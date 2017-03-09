---
layout: essay
type: essay
title: 'Meteor Gotchas'
date: 2017-03-09
labels:
  - Software Engineering
  - Meteor
---

## Introduction
When you're starting out with meteor, it can be a real pain because there are so many little things you have to pay attention to. This includes learning all the commands, the file structure, and even how all the files communicate with each other when you finally start building the actual we application. One of the hardest things to handle with meteor is when you have encountered a problem and do not know how to fix it at all, but when you finally figure out how to fix it, it feels so great. In my software engineering class, we currently have to develop a web application called "Digits" which introduces all necessary concepts to build a meteor application, and boy, have I had some trouble.

## Problems Encountered

### 1. File Structure
One of the main problems I've encountered is how the files are structured in the meteor application. There are so many directories with tons of files inside of it. This includes: client, imports, server, and public. Many of these directories have JavaScript files along with some HTML file as well, so when you want to find out how to change a simple element on header, it can be difficult to sift through each and every directory to find that simple html file named "header.html".

### How I fixed it
The way I fixed this problem was by simply learning how the file structure is set up. This includes learning it at a conceptual level in the sense that the placement of each file should make perfect sense conceptually. I read up on the documentation to figure out the function of each directory and the implementation concept behind them.

### 2. Templates
Another "weird", but kind of cool thing with meteor is the use of Templates. When I first had to get the template from the premade repository on github, it was really confusing on how to implement the template correctly without any errors. Our professor had us create the application directory, download the zipped template from a repository on github and then expand and run a few commands: `meteor npm install` and `meteor --settings ../config/settings.development.json` . For me, it was confusing to know exactly what these commands meant on the spot, especially the "settings" command.

### How I fixed it
Documentation! Documentation is really helpful with any sort of development that you do. I read through the documentation for the templates as well as the commands. Getting to learn the commands and command syntax for meteor is really helpful and can really solve some problems that you may have with what ever you are doing.
