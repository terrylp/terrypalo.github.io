---
layout: essay
type: essay
title: "Structuring your files is important too!"
date: 2017-09-10
labels:
  - Structure
  - Files
  - Testing
---

## Introduction
Switching from testing this week, I wanted to write about the significance of structuring files for a project. One of the projects I am working on fixing/upgrading has all sorts of issues. These issues range from bugs within the code itself, to build issues. 

## Things I Noticed
One of the first things I did when I was handed the source code to the project was analyze the project itself. I noticed its massive size for a relatively small project. I realized the reason for this being was that most of it was temp data, as well as per-user files. When I ran the project, the application was bug-ridden, but that is beside the point of this writing.

<img class="ui medium right spaced image" src="../images/oh-god.gif">

### Adding a .gitignore
I decided that the project needed a .gitignore in order to fix the sizing issue. Since its a Visual Studio based project, I added the VisualStudio.gitignore from [here](https://github.com/github/gitignore/blob/master/VisualStudio.gitignore) (great resource by the way!). I applied the .gitignore to the project:

```
git rm -r --cached .
git add .
```

As a result, the project was significantly smaller.

## Where File Structuring Plays a Role
After adding the .gitignore, a coworker pulled the resulting project, and tried to build it, but it kept failing. After debugging and tracing errors, I found that when the project was being developed, some of the developers placed dependencies in the bin folder.  In the VisualStudio.gitignore, the bin folders were all ignored.

<img class="ui medium right spaced image" src="../images/putting-2-2-together.gif">

### The Structure
If the developers simply planned how they would structure their files, then there would not have been any complications at all with the .gitignore.

## My Thoughts
Personally, I feel like file structure isn't only a way to organize your mess, but it also plays a key role in technical aspects, like the case where placing dependencies in bin broke everything. Having an organized project can also make it more efficient for development too. There have been times where I can simply pick up a project and easily start contributing to development. Some of my earlier personal projects that I have worked on were a complete disaster, i think, for the sole reason of bad organization. I easily got lost in the mess of a bunch of files, and lost motivation to even try and fix it.









