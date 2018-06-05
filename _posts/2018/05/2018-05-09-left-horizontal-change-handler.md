---
layout: post
title: 'HorizontalChangeHandler sliding from/to the left'
categories: [Programming]
tags: [Android, Martin Fowler]
date: 2018-05-09 05:15:00 PM UTC
---

<!-- May 10, 2018 01:15:00 AM Philippine Time -->

> "**I'm a very lazy programmer.** One of my forms of laziness is that I never remember things about the code I write. Indeed, I deliberately try not to remember anything I can look up, because I'm afraid my brain will get full. I make a point of trying to put everything I should remember into the code so I don't have to remember it."
<br /><br />
> --- Martin Fowler (from his Refactoring book, p. 56)

Another form of laziness that we, programmers, have is to not rewrite anything that is already written by other programmers.

<!--more-->

But how would we know if the code we want to write is already written by other programmers?

By googling for it, of course! :smile:

That might be the reason why you are in this page! --- You are using [Conductor](insert link here) in your Android app, and you want an `AnimatorChangeHandler` which slides your screens from/to the left... and you are lazy (or, as in my case, do not know how to do it :smile:)... so you googled for it.

I tried it... _and found none_.

So I created one myself --- I just copied the [code for the `HorizontalChangeHandler` provided by Conductor](insert link here) and then made some changes to it.

I hope this helps my fellow lazy programmers!

Here it is:


``` java
import android.animation.Animator;
import android.animation.AnimatorSet;
import android.animation.ObjectAnimator;
import android.support.annotation.NonNull;
import android.support.annotation.Nullable;
import android.view.View;
import android.view.ViewGroup;

import com.bluelinelabs.conductor.ControllerChangeHandler;
import com.bluelinelabs.conductor.changehandler.AnimatorChangeHandler;

public class LeftHorizontalChangeHandler extends AnimatorChangeHandler {

    public LeftHorizontalChangeHandler() { }

    public LeftHorizontalChangeHandler(boolean removesFromViewOnPush) {
        super(removesFromViewOnPush);
    }

    public LeftHorizontalChangeHandler(long duration) {
        super(duration);
    }

    public LeftHorizontalChangeHandler(long duration, boolean removesFromViewOnPush) {
        super(duration, removesFromViewOnPush);
    }

    @Override @NonNull
    protected Animator getAnimator(@NonNull ViewGroup container, @Nullable View from, @Nullable View to, boolean isPush, boolean toAddedToContainer) {
        AnimatorSet animatorSet = new AnimatorSet();

        if (isPush) {
            if (from != null) {
                animatorSet.play(ObjectAnimator.ofFloat(from, View.TRANSLATION_X, from.getWidth()));
            }
            if (to != null) {
                animatorSet.play(ObjectAnimator.ofFloat(to, View.TRANSLATION_X, -to.getWidth(), 0));
            }
        } else {
            if (from != null) {
                animatorSet.play(ObjectAnimator.ofFloat(from, View.TRANSLATION_X, -from.getWidth()));
            }
            if (to != null) {
                // Allow this to have a nice transition when coming off an aborted push animation
                float fromLeft = from != null ? from.getTranslationX() : 0;
                animatorSet.play(ObjectAnimator.ofFloat(to, View.TRANSLATION_X, fromLeft + to.getWidth(), 0));
            }
        }

        return animatorSet;
    }

    @Override
    protected void resetFromView(@NonNull View from) {
        from.setTranslationX(0);
    }

    @Override @NonNull
    public ControllerChangeHandler copy() {
        return new LeftHorizontalChangeHandler(getAnimationDuration(), removesFromViewOnPush());
    }
}

```

