---
layout: essay
type: essay
title: "Asynchronous Code: Fun"
date: 2017-09-03
labels:
  - Testing
  - Nightwatch
  - Asynchronous
---

## Introduction
On my previous post about Nightwatch, I explained what Nightwatch was, how I typically use it, problems faced and new approaches to using it because of those problems. One of the problems I have always faced, and I didn’t mention on my last post, and more importantly ran into last week is the Asynchronous nature of Nightwatch.

## Asynchronous?
In case you might not know what asynchronous programming might be, it is when multiple threads do work concurrently on a piece of code. If you do not understand specifically what they are doing then you can be confused and it will be really hard to figure out how to fix bugs. 

### In JavaScript
In JavaScript, asynchronous programming is a little different from other programming languages. In JavaScript, you are not able to create new threads, but JavaScript itself will perform multithreading if it needs to depending on the situation (like performing database queries, and http requests). You can typically control asynchronous JavaScript code with callbacks, but it can become a total mess.

<img class="ui medium right spaced image" src="../images/callback.png">

### In Nightwatch
Since Nightwatch uses node.js, there are a ton of asynchronous pitfalls to watch out for. If you’re new to using Nighwatch and asynchronous code, then you will definitely fall into them like I did (still am!). Nightwatch has an API with different [commands](http://nightwatchjs.org/api#commands) that you can use, and most of those commands use the Selenium JsonWireProtocol. Essentially, this can become an asynchronous mess if you do not know what you are doing or how the commands work.

## Asynchronous Code at Work
At work, there is a project I'm working on that has items that are associated with keys, and each of those keys are manually assigned to each item upon creation. These items can be assigned to users or deleted. If they are deleted, they aren't *completely* deleted, meaning that the keys are still associated with the item.

I'm creating frontend tests to create, assign and delete these items. Since these tests are going to be used in a CI/CD server and be completely automated, I need to find a way to generate a key that has not been used on current *and* deleted items.

There is a location on the project that will show all the item keys, so I decided to create a preliminary script to generate a key and check it by looking at all the item keys on that page.

This is where everything goes wrong.

### The Problem
My pseudocode for generating they key was:

```
randomKey = generateRandomKey()

// While its visible, generate a new key and try again
while (find(randomKey)) {
    randomKey = generateRandomKey()
}
```

My pseudocode for checking if key was unique:
```
// Return true if it is visible on the page
find(key) {
    return browser.isVisible('#item[value=' + key + ']')
}
```

Seems simple enough, right? Wrong.

The problem with this is that, because of Nightwatch's asynchronous nature, there is an issue with putting the asynchronous command (isVisible) inside of a while loop. The while loop will never wait and will continuously run. I played with the code for a little while then decided to find a totally different way of going around this.

<img class="ui medium right spaced image" src="../images/head-desk.gif">

### Solution
I figured my original solution was very inefficient anyway, so I decided to simply grab all the item elements with a simple:
`document.querySelectorAll('#item')` 
, adding each element key to an array, then checking if a generated key is unique based off that array.

<img class="ui medium right spaced image" src="../images/success.jpg">



