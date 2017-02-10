---
layout: essay
type: essay
title: "Why do I have to write it like this? "
date: 2017-01-20
labels:
  - "Coding Standards"
  - Reflection/Review
---


## Introduction
Recently, a professor for my Software Engineering class introduced us to IntelliJ with ESLint for use with JavaScript. IntelliJ is an integrated development environment, or commonly known as, an IDE. ESLint is a linting utility which basically checks syntax and use of JavaScript syntax to make sure that it adheres to certain style guidelines. In my class, we used the AirBnB JavaScript style guideline.

Sounds pretty awesome right? Well it is, except it can be frustrating at first to get used to.

## ESLint Itself
While trying to make a simple JavaScript program, I found it frustrating to get that pesky green checkmark that IntelliJ shows if your code does not have any errors *and* adheres to the the style guideline from ESLint. For example, when I was writing some simple output of a value: ``console.log("The output is " + someValue)`` usually JavaScript itself would not complain whether you use (" ") or (' ') to indicate a string or even if there is a semi colon at the end of the line, but with the AirBnB style guidelines you *must only* use (' ') and *always* have a semicolon at the end of a line. Fortunately, with IntelliJ, if there are any errors, you can automatically allow the it to fix your code for you. This helps most of the time, but from my experience it does not work for unused variables/functions. So as a result, when you first start out, and you're not used to, you may ask yourself "Why is this even necessary? This is completely useless!" But luckily, there are some really good things that come out of style guidelines.

<img class="ui medium right spaced image" src="../images/head-desk.gif">

## The Pros
Since I have already, indirectly, pointed out the cons of ESLint and style guidelines, I'll go ahead and point out the pros. Personally, having a little bit of experience working with other developers in web development, things can become a bit messy. When multiple developers work on the same piece of code, chances are that they all have their own particular way of writing code. With style guidelines and linting tools like ESLint that ensures that code follow these guidelines, this allows for developers to easily read and follow code written by someone else.

Some people also think that these "coding standards" actually help people learn a programming language. Although I have not necessarily experienced it myself, I can see why people may think this. If there are certain rules to follow by with code, this allows someone who is beginning to learn a language less options on how to do things, which may result it less error caused by unviable ways of coding.


## Overall
I personally think IntelliJ with use of ESLint is really cool even though it is pretty frustrating when I first got to using it. I can totally see myself using it more in the future to keep myself organized on projects (or to even clean up projects that I have right now!).
