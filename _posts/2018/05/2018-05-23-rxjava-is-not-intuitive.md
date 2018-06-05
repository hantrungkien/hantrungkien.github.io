---
layout: post
title: 'RxJava is not intuitive... and what helped me to somewhat understand it'
categories: [Programming]
tags: [Android, RxJava, Retrofit, Jake Wharton, Dan Lew]
date: 2018-05-23 08:45:00 PM UTC
---

<!-- May 23, 2018 04:46:00 AM Philippine Time -->

> "Functional reactive programming is not intuitive."
<br /><br />
> --- Dan Lew (in his ["Introduction to Functional Reactive Programming"](http://blog.danlew.net/2017/07/27/an-introduction-to-functional-reactive-programming/))


<!--more-->
-----

**TLDR:** Just read the last section of this post: ["Some help that can make RxJava more understandable"](#some-help-that-can-make-rxjava-more-understandable)

-----

More than a year ago, I started being involved in Android mobile development.

Lucky me, the project I was involved in was using RxJava, which they say makes multithreading much easier. 

You see, a mobile app needs to be very responsive to the users, or else the users will throw their phones against the wall, and their phones will break, together with the app. Multithreading solves that problem --- we do the UI stuffs in the _UI thread_, and we do the I/O stuffs in the _IO thread_, so that the UI will still be responsive to the users even when the I/O stuffs takes too long to execute.

<!-- put picture of phone being thrown here -->



So... I was a beginner RxJava-ist... And this is how I used it during my first _many_ weeks:

In the code below, notice the `DataSource` and `Presenter` classes --- I pass an `Observer` into the `getData()` method of `DataSource`.

``` java
public class Data {
    public String id;
}

// We were using Retrofit for getting and sending data through the network.
public interface DataRetrofitService {
    @GET("/data")
    Observable<Data> getData();

    @GET("/data/{id}/details")
    Observable<Details> getDetails(@Path("id") String id);
}

public class DataSource {
    DataRetrofitService dataRetrofitService;
    ...

    public void getData(Observer<Data> observer) {
        dataRetrofitService.getData()
                .subscribeOn(Schedulers.io())
                .observeOn(AndroidSchedulers.mainThread())
                .subscribe(observer);
    }
    
    public void getDetails(String dataId, Observer<Details> observer) {
        dataRetrofitService.getDetails()
                .subscribeOn(Schedulers.io())
                .observeOn(AndroidSchedulers.mainThread())
                .subscribe(observer);
    }
}

public class DataPresenter {

    private DataSource dataSource;
    private DataView view;

    public void showData() {
        dataSource.getData(new Observer<Data>() {
            @Override
            public void onCompleted() {
            }

            @Override
            public void onError(Throwable e) {
                view.showError("an error occured");
            }

            @Override
            public void onNext(Data data) {
                view.show(data)
            }
        });
    }
}
```

So far so good. No problems... _Easy!_

Then came the time where I had to execute two network calls in a sequence --- _do this network call, then after that do this other network call._

In an imperative style programming, that would look something like this

``` java
try {
    Data data = dataSource.getData()
    Details details = dataSource.getDetails(data.id)
    view.show(details)
} catch () {
    view.showError("an error occured");
}
```

_That would be easy to do using RxJava!..._

``` java
    public void showData() {
        disposable = dataSource.getData(new Observer<Data>() {
            @Override
            public void onCompleted() {
            }

            @Override
            public void onError(Throwable e) {
                view.showError("an error occured");
            }

            @Override
            public void onNext(Data data) {                        
                dataSource.getDetails(data.more, new Observer<Details>() {
                    @Override
                    public void onCompleted() {
                    }

                    @Override
                    public void onError(Throwable e) {
                        view.showError("an error occured");
                    }

                    @Override
                    public void onNext(Details details) {
                        view.show(details)
                    }
                });
            }
        });
    }
```

_Yehey!... But it looks so ugly._

And because I know (assume) that the creators of RxJava have a better sense of beauty than I do, they must have _not_ designed it to be used in that ugly kind of way.

I have to turn to the most beloved tool that programmers of my kind use today: 

> **Me:** Google, please tell me how to "RxJava finish one observable before executing another one".
<br /><br />
> **Google:** Huh!... Okay, here are the documents with the keywords "RxJava", "observable", "finish", "before", and "another" in them.

... After reading some of the articles... _Oh no!_ I think I have been using RxJava in a wrong way!

This is what people get when they make the assumption that _"if it is currently working, then it must be right"._

And I'm sure I will be making that assumption a lot later in my life. I hope not that much anymore.

Okay, enough of that... seems like the correct way of doing it is like this:

_All your methods must **return observables all the way up** [from the data source to the presenter, for example],_ then use the RxJava operators, such as `flatMap()`, to compose the observables.

In the code below, notice the methods in the `DataSource` class --- they do _not_ receive an `Observer` anymore, and they now return an `Observable` instead of `void`.

``` java
public class DataSource {
    public Observable<Data> getData() {
        return dataRetrofitService.getData();
        // you can also do something like
        //      return dataRetrofitService.getData()
        //          .flatMap(data => { 
        //              // save data to database
        //          });
    }
    
    public Observable<Details> getDetails(String dataId) {
        return dataRetrofitService.getDetails();
    }
}

public class DataPresenter {
    public void showData() {
        disposable = dataSource.getData()
            .flatMap(new Func1<Data, Observable<Details>>() {
                @Override
                public Observable<Details> call(Data data) {
                    return dataSource.getDetails(data.more);
                }
            })
            .subscribeOn(Schedulers.io())
            .observeOn(AndroidSchedulers.mainThread())
            .subscribe(new Observer<Details>() {
                @Override
                public void onCompleted() {
                }

                @Override
                public void onError(Throwable e) {
                    view.showError("an error occured");
                }

                @Override
                public void onNext(Details details) {
                    view.show(details)
                }
            });
    }
}
```

So a typical method with this signature

``` java
public Data getData()
```

will be replaced by

``` java
public Observable<Data> getData()
```


A method with a `void` return type

``` java
public void doThis()
```

will be replaced by

``` java
public Observable<Void> doThis()
```

Or in the case of RxJava 2, it will be replaced by

``` java
public Completable doThis()
```

## Tutorials

So how did I come to better understand how to use RxJava?

... through Dan Lew's tutorials, which I found recommended in the comments section of [an article](https://medium.com/@jagsaund/5-not-so-obvious-things-about-rxjava-c388bd19efbc) a coleague shared:

- [Grokking RxJava, Part 1: The Basics](http://blog.danlew.net/2014/09/15/grokking-rxjava-part-1/)
- [Grokking RxJava, Part 2: Operator, Operator](http://blog.danlew.net/2014/09/22/grokking-rxjava-part-2/)
- [Grokking RxJava, Part 3: Reactive with Benefits](http://blog.danlew.net/2014/09/30/grokking-rxjava-part-3/)

And through Jake Wharton's talk ["Exploring RxJava 2 for Android - GOTO 2016"](https://www.youtube.com/watch?v=htIXKI5gOQU), which was also shared to me by a coleague.



## Some help that can make RxJava more understandable

And please note that even masters such as Jake Wharton and Dan Lew say that RxJava is **not intuitive on first enconter**. These quotes below might help you go in the right direction when trying to _grok_ RxJava...

In an interview (["Reactive Extensions, RxAndroid, Optimization (Android Dialogs)"](insert link here])), Jake Wharton said this:

> "**It's a different way of thinking**, but once you get that way of thinking, you **start seeing everything as streams** and how to compose them and break them apart just to create these different pieces of your app."
<br /><br />
> "**It's very hard to break out of the so called "imperative way"**, where you just want to write an `if`, or you just want to store something in a field or local variable for use inside of a callback or another method later... **You have to basically unlearn that way** and realize that there are ways built into this pattern, the reactive pattern, that accomplish the same goals, just in a completely different way. **And once you switch that way of thinking, hopefully it becomes a lot easier.**"

In ["Grokking RxJava, Part 2"](http://blog.danlew.net/2017/07/27/an-introduction-to-functional-reactive-programming/), Dan Lew said something about this code below:

> ``` java
query("Hello, world!")
    .flatMap(urls -> Observable.from(urls))
    .subscribe(url -> System.out.println(url))
```
> "...**`flatMap()` is weird, right?** 
<br /><br />
> Why is it returning another `Observable`? The key concept here is that the new `Observable` returned is what the `Subscriber` sees. It doesn't receive a `List<String>` --- it gets a series of individual `Strings` as returned by `Observable.from()`.
<br /><br />
"**For the record, this part was the hardest for me to understand**, but once I had the **"aha" moment** a lot of RxJava clicked."

I hope these things will make RxJava a little more intuitive to you too!

And if I said something wrong above, please say so in the comments.
