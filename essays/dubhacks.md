---
layout: essay
type: essay
title: "You don't have to go to a top university to make great software."
date: 2017-10-23
labels:
  - Dubhacks
  - Hackathon
---

## Introduction
Instead of talking about what I did last week at work, I wanted to talk about my experience with the largest hackathon in the pacific northwest called Dubhacks. 

Earlier this year I heard about Dubhacks and how they offered students travel reimbursement based on an application. So I sent in my application that included my resume and answers to a few questions, and lucky enough, I was accepted along with travel reimbursement to fly out to Seattle. Another ICS student at UH (Jon Robello) got accepted too, so we decided to team up and take on teams from all around the world. 


## What is Dubhacks
Dubhacks is the largest hackathon in the pacific northwest hosted by the University of Washington. The hackathon is sponsored by a ton of companies including: Facebook, Google, Microsoft, and Amazon. There are 3 primary challenges that are offered to the competitors, and the sponsors have their own smaller challenges that as well. During the hackathon itself they offered meals, snacks, energy drinks, and even activities to all the competitors. This year was the largest turnout with over 700 competitors as well as over 100 teams. 

<img class="ui medium centered image" src="../images/dubhacks.svg">

## My Experience 

### The Team
Since Jon and I went to dubhacks together with no team, we joined a team formation event and found 3 other teammates that we decided to work with. This was their first hackathon, and even their first time touching JavaScript/TypeScript frameworks. 

### The Idea
We wanted to take on Challenge 1, which stated: 

Reimagine a tool of today to cultivate equity and access for everyone tomorrow.

We decided to create an app that could not only help the general population, but help the visually impaired greatly. Our idea was to create an app that could be placed on a dashboard of a vehicle, and would use machine learning to tell a user whether or not there are stop signs, traffic lights, or even pedestrians that you would need to be extra aware of. We also allowed real-time geolocation data to access historic location data about traffic, and accidents to allow a user to be aware of this while they drive. A text to speech voice would then speak to the user while they drive to get important information that they need to be aware about.

### The Techstack
Our techstack was:

- Ionic 
- Microsoft Cognitive Custom Vision AI API
- Shine API 
- a little bit of tears

We decided to use Ionic because it included all the features we needed, Camera, Geolocation, and an easy to use css framework. The Custom Vision AI API was perfect because it allowed us to use specific training data to create models to look for. It looked for traffic lights, stop signs, and even pedestrians. We used Liberty Mutual's Shine API, for historic location data.
And of course, a little bit of tears to let out some stress.

### The Development
During this Hackathon, I contributed to more software design than I did coding, although I felt like I still did a lot of coding. Since we had 3 other people on our team that were completely new to the frameworks that we were using, I had to design the project development in a way that was intuitive and easy to pick up. I assigned tasks and regularly checked up on everyone’s progress to make sure they weren't stuck and I could give them the help they needed.

### The Result
We finished up with a prototype that was working as intended even though we had some bugs (but that’s pretty inevitable with a project made in 24 hours). With a hackathon at this size it was kind of a challenge to have all projects presented and judged in a short amount of time. Everyone had their own designated spot in a room and all the challenges that you signed up to compete for would come and judge your project. If you signed up for a main challenge then they would pick the top 2 projects for that particular challenge and have them create a final presentation for all 700 participants and final judges.

Our project did surprisingly well compared to the other 48 teams that signed up for our particular challenge, and we were able to do a final presentation. We did our presentation, but unfortunately, we didn't win (but that's okay!). 

<div class="ui grid">
  <div class="four column row">
    <div class="column">
        <img src="https://challengepost-s3-challengepost.netdna-ssl.com/photos/production/software_photos/000/557/006/datas/gallery.jpg">
    </div>
    <div class="column">
        <img src="https://challengepost-s3-challengepost.netdna-ssl.com/photos/production/software_photos/000/557/008/datas/gallery.jpg">
    </div>
    <div class="column">
        <img src="https://challengepost-s3-challengepost.netdna-ssl.com/photos/production/software_photos/000/557/007/datas/gallery.jpg">
    </div>
    <div class="column">
        <img src="https://challengepost-s3-challengepost.netdna-ssl.com/photos/production/software_photos/000/557/005/datas/gallery.jpg">
    </div>
  </div>
</div>

## Thoughts
I feel like people who do these hackathons, don’t immediately expect to win, so they have this mindset of creating something really small with the most minimal effort possible. Out of all the hackathons I've participated (only 3), I can see that people aren't ambitious with their projects, and truly underestimate the kind of development they can produce. 

## Outcome
Even though our team didn't win, it felt great knowing that we have the ability to create software that competes with other teams from top computer science schools in the world (like UW). This hackathon was completely different from the other hackathons that I have attended in the way that I felt like more of a mentor rather than a developer. It felt really rewarding to teach these 3 new people on our team how component based front end frameworks work, and how to create http requests to an API to create something amazing.










