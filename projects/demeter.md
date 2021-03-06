---
layout: project
type: project
image: images/demeter-equal.png
title: Demeter
permalink: projects/Demeter
date: 2017
labels:
  - Meteor
  - Bootstrap
  - "AT&T M2X"
summary: Gamified plant monitoring system that won 1st Best IoT Solution at the 2017 AT&T Hackathon.
---

## Summary
Created a gamified plant monitoring system equipped with a Raspberry Pi along with light, temperature, and humidity sensors. Developed for the 2017 AT&T Hackathon in Honolulu, and ultimately won 2/8 total awards.

Features included:
* Color coordinated plant health status
* Profile with achievements
* Community similar to StackOverflow, but for plants 


## How We Built it
We created this application with Meteor, and used a Raspberry Pi to post data to AT&T M2X Database aimed for use on IoT devices.

## Personal Responsibilities
Personal responsibilities to this project included:
* Set up the sensors on the Raspberry Pi.
* Create the Python script to gather and send humidity, temperature, and light data from the Raspberry Pi to the M2X database.
* Set up the Meteor application to gather the resulting data from the M2X API and display results.
* Assist with connecting the front-end UI with the Meteor web application.

## The App Itself

<div class="ui grid">
  <div class="three column row">
    <div class="column">
        <img src="../images/demeter-home.png">
    </div>
    <div class="column">
        <img src="../images/demeter-profile.png">
    </div>
    <div class="column">
        <img src="../images/demeter-community.png">
    </div>
  </div>
</div>

Recap on the [2017 AT&T Hackathon](https://developer.att.com/blog/recap-hackathon-hawaii-2017)




