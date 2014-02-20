---
author: juanpintoduran
title: 'My 1st month with TDD or "Why TDD is a pain in the ass but you should learn and use it anyway"'
excerpt:
layout: post
categories:
  - Developer Life
tags:
  - rails
  - ruby
  - tdd
  - rspec
post_format: [ ]
---

This story begins with a developer, 1 month ago who didn't write a single test in his life (Me). In it's first day at his [new work](http://acid.cl), his Project Leader gives him a tremendous brief on how use Git and Rspec. The first part of the brief is another history, but the second was just a glance of what all TDD means.

As you will know, *TDD* stands for **Test-Driven Development** and is a method for writing good, reusable and mainteinable code. Also, if you read the blog often (or just the sidebar) you will know that I work with **Ruby on Rails**, and in this specific case, we use a Gem, called **RSpec** instead of the "out-of-the-box" **TestUnit** that rails brings itself.

At first, TDD is a pain in the ass, why? Cause TDD most fundamental basis stands in 2 statements:

+ You should write test before coding (or later and then test commenting your code) and see it failing.
+ You should test *every single feature*

It sounds pretty bad cause even testing some feature like "The header shows the current user name" should have a test, in that case, it suppose to use also a *Factory* (provided via **FactoryGirl**) and set the current user (i.e. with Devise current_user helper method), and then look for a CSS tag that provides the user name. Sounds tricky for a thing that you should never going to see again and that maybe you done a hundred times before starting this project... But it's necessary.

I did not understand this at first place, it was hard for me to put my skills tested by myselft in thing that I consider trivial for an average programmer. But then my PL shows me the meaning of the test... That's not for me, or maybe it is, but the test needs to be done cause if another programmer or me override the current_user method, or we replace Devise, or the user has no name, the test will fail and we will know where is it, and hopefully, how to fix it quickly.

So, with that in mind I started to write test for every-single-feature and it gets easy each day. It's even fun to try write the perfect test without the code in the app and see it passing partially when you write the code. It saves me time when merging also, cause if all test passes in green, then my merge is a piece of cake.

After this first month from writing my first view test (obviously you can write test for controllers, models, helpers and initializers, and even make the test suite to take screenshots of your partials!) I can't say anything against TDD, cause it's awesome, it saves you time, it gives you free time on weekends and definitely makes you more as a developer and less of a simple programmer.

P.S.: BTW I will write another post with a simple guide to get started with TDD this week, stay tunned and download the Android app, some day I will write Push Notifications on that thing.