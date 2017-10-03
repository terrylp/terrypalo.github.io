---
layout: essay
type: essay
title: "A Continuation on DRF"
date: 2017-10-02
labels:
  - Django
  - DRF
  - "Bug Fixing"
---

## Introduction
Recapping from last week, I spoke about my experience with Django Rest Framework so far with this project and the issues that I am currently facing, such as restructuring the project, and the issue of updating multiple models at the same time. 

_Good News_, I was able to completely fix those issues and was able to create a really solid REST API.

<img class="ui medium centered image" src="../images/its-working.gif">

## How I fixed it
So last week, I had to figure out how to update multiple multiple models through a POST request. There were a couple of things I had to watch out for but the main one were Validators

### Validators
Django Rest Framework is pretty cool because it supplies an is_valid() function that must be called prior to creating models in the database from a POST request. This is useful because it ensures that data is not malformed, and the data follows the current model schema, so there are no issues when saving a new model into the database.

_Although_ this can be pretty annoying especially when you have some custom login on models.

For example, continuing on with the car - person example I had last week:

Model A:

* car_name

Model B:

 * car_name
 * person_name

When I create a POST request to create a new Model A, I also need to use the JSON Web Token to verify the person and assign the car + person relation on Model B. 

The point of this is to keep all unique cars in Model A, and behind-the-scenes keep track of which people are allowed to access which cars.

Seems straightforward right? _kinda_

In order to create a post request I need to validate the data, which is fine, but by default the DRF is_valid() function keeps track of Model characteristics. So in this case, Model A car_name is a unique field so if another user tries to create a car_name via POST request, then the is_valid function will raise an error saying "This car already exists."

I was trying to avoid making POST requests directly to Model B, so this whole serializer + view can only reference Model A (to remain consistent). But, after redesigning and approaching the problem differently I figured it would be better if I just went ahead and posted to this Model instead. 

<img class="ui medium centered image" src="../images/bugs-morebugs.gif">

(Accurate depiction of me trying to squash these bugs)

## Things I'd like to improve in the future
I think most of the mistakes I'm making with this current project stem from not testing my work as much as I should. So one of the things I really need to work on going forward would be creating tests prior to development (Test-driven development, perhaps?). 

Another thing I'd like to do next time is really sit down and spend more time designing the relational database. I modeled this application last year, and it was my first time actually designing a relational database so I was bound to make mistakes. I find myself right now realizing different ways of how I could have approached this a little better. 

