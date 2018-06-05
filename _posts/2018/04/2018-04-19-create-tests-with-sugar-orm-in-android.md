---
layout: post
title: How to create tests when you are using Sugar ORM (version 5) in an Android app
categories: [Programming]
tags: [Android, Sugar ORM, Java, Testing]
date: 2018-04-19 05:00:00 PM UTC
---

<!-- April 20, 2018 01:00:00 AM Philippine Time -->

Let's say that in your Android application, you are using Sugar ORM in your data source class, which does the [CRUD](http://www.skorks.com/2010/03/you-dont-need-math-skills-to-be-a-good-developer-but-you-do-need-them-to-be-a-great-one/) to your local database.

``` java
import com.example.domain.MyDataSource;
import com.example.domain.MyEntity;
import com.example.data.MyDbModel;

import io.reactivex.Completable;

public class MyRepository implements MyDataSource {

    public Completable save(MyEntity myEntity) {
        return Completable.fromAction(() -> {
            MyDbModel myDbModel = new MyDbModel(myEntity.id());
            SugarRecord.save(myDbModel);
        });
    }

    public Single<MyEntity> get(UUID id) {
        return Single.fromCallable(() -> {
            // TODO: Select.from(MyDbModel.class)...
        });
    }

}
```

... And you want to make tests for you `save()` method (some call this integration tests, instead of unit tests, because these tests touch the database).

<!--more-->

You have to add the `SugarOrm.init()` in your setup method and the `SugarOrm.terminate()` in your cleanup method, like in the code below.

``` java
import android.app.Activity;
import io.reactivex.observers.TestObserver;
import org.robolectric.RobolectricTestRunner;

...

@RunWith(RobolectricTestRunner.class)
@Config(constants = BuildConfig.class, 
sdk = Build.VERSION_CODES.KITKAT, manifest=Config.NONE)
public class MyRepositoryIntegrationTests {

    @Before
    public void setup() {
        SugarOrm.init(Robolectric.buildActivity(Activity.class)
                .create()
                .resume()
                .get());
    }

    @After
    public void cleanup() {
        SugarOrm.terminate();
    }

    @Test
    public void saveTest() throws Exception {
        // arrange
        TestObserver saveObserver = new TestObserver();
        UUID newId = UUID.randomUUID();
        MyEntity myEntity = new MyEntity(newId);
        MyRepository repository = new MyRepository();

        // act
        repository.save(myEntity).subscribe(saveObserver);

        // assert
        saveObserver.assertComplete();
        saveObserver.assertNoErrors();

        TestObserver<MyEntity> getObserver = new TestObserver<>();
        repository.get(newId).subscribe(getObserver);

        getObserver.assertComplete();
        getObserver.assertNoErrors();
        getObserver.assertValueCount(1);
        getObserver.assertValue(entity -> entity.id().equals(newId));
    }

    ...

}

```

You can also choose to put the SugarORM `init()` and `terminate()` in a base integration tests class like the one below:

``` java

@RunWith(RobolectricTestRunner.class)
@Config(constants = BuildConfig.class, 
sdk = Build.VERSION_CODES.KITKAT, manifest=Config.NONE)
public abstract class BaseDataIntegrationTests {

    @Before
    public void setupFromBase() {
        SugarOrm.init(Robolectric.buildActivity(Activity.class)
                .create()
                .resume()
                .get());
    }

    @After
    public void cleanupFromBase() {
        SugarOrm.terminate();
    }
}
```

_(Be sure that the name of your setup method in this base class is **different** from the name of the setup methods in your child classes, because if they are the same, the setup method of the base class will be overriden, and so the `SugarOrm.init()` will never be invoked.)_

... Then make _all_ your database integration tests inherit from it.

``` java
public class MyRepositoryIntegrationTests 
    extends BaseDataIntegrationTests {
    ...
}
```

Of course, I understand that these kinds of tests are _useless_ if _all_ you are doing in your `repository.save()` method is call the `SugarRecord.save()` method. :laughing: The Sugar ORM people already tested their work, I believe. We do not need to retest them.

These kinds of tests will be useful if, for example, you have to test that your `save()` throws a particular `Exception` if a specific thing occurs in `save()` method; or you have to do other things, such as save your data to a server, and things like that...

And I also understand that in an enterprise kind of application, the [repositories are not supposed to have a `save()` method](https://programmingwithmosh.com/entity-framework/common-mistakes-with-the-repository-pattern/). :laughing:

But I'm hoping that this tutorial will help someone who needs to test something that uses Sugar ORM.

Happy coding!!!
