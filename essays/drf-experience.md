---
layout: essay
type: essay
title: "Django Rest Framework: An Experience"
date: 2017-09-25
labels:
  - Django
  - DRF
---

## Introduction
As discussed last week in my previous writing, I'm assigned a project currently where I have to create a REST API for a Django application that I have made previously. 

This project is interesting because I'm adding a REST API to an already full stack Django Application. From what I've noticed, its usually one or the other. Theres either a full stack Django application or just a REST API built by Django Rest Framework. 

<img class="ui right spaced image" src="http://www.django-rest-framework.org/img/logo.png">

## My Experience So Far
Currently, the project is going pretty well. I've had to restructure the project slightly so I dont repeat myself. One of the main things I've had to restructure was the way services are handled in the application. 

### Restructuring
In the original full stack project I had a file structure such as:

```
Django_project
│
└───Component_1
│   │   models.py
│   │   apps.py
│   │   urls.py
│   │   services.py
│   │   views.py
│   │   admin.py
│   
└───Component_2
│   │   models.py
│   │   apps.py
│   │   urls.py
│   │   services.py
│   │   views.py
│   │   admin.py
│
```


So when I had to create an API for the project I added an API folder to hold all the components associated to it and restructured it a little.

```
Django_project
│
└───Component_1
│   │   models.py
│   │   apps.py
│   │   urls.py
│   │   views.py
│   │   admin.py
│   
└───Component_2
│   │   models.py
│   │   apps.py
│   │   urls.py
│   │   views.py
│   │   admin.py
│
└───api
│   │
│   └───Component_1
│   │   │   apps.py
│   │   │   serializers.py
│   │   │   views.py
│   │
│   └────Component_2
│   │    │   apps.py
│   │    │   serializers.py
│   │    │   views.py
│
└───services
│   │   component1_service.py
│   │   component2_service.py
```

As you can see, I added a whole api directory with the associated components, and since both the api and full stack application reference the same service, I went ahead and followed a dependency injection model and created a services folder.

I decided to create a whole new api directory because it seems cleaner and easier to maintain in the longrun, rather than trying to figure out later on what belongs to the full stack application and what belongs to the api. 

So far everything seems to be working really smoothly. It is really easy to follow along with this structure, but then again, I'm the one who created it. 


### Issues I'm having
One of the issues that I'm currently facing is that I have to update/create a model when someone makes a post request on a particular model.

For example, say we have:

Model A:
    - car_name

Model B:
    - car_name
    - person_name

So model A contains unique car names, and model B contains car_name as a foreign key to car_name in model A (for a many to one relationship). This will allow different people to be associated to a particular car name.

The problem I have is that I need to update 2 models when someone makes a post request to create a new car_name. The way I'm approaching this is by creating a serializer to create the model when it recieves the raw data from a request. I just recently tried it out, and it seems to break every time. It might be because I dont fully understand how the viewsets and the serializers interact with eachother.

So the goal for this week is to figure it out and create a superior API.

<img class="ui right spaced image" src="https://m.popkey.co/96857f/oGkQD.gif">
(Me charging towards this bug)











