---
layout: essay
type: essay
title: "Keeping your APIs authenticated one step at a time."
date: 2017-09-17
labels:
  - Django
  - DRF
  - JWT
---

## Introduction
I was assigned another project recently to further upgrade a current Django application that I developed earlier this year. I created a complete Django application earlier this year that allowed users to log in, view relevant data pertaining to them in a table format, which allowed sorting and searching by fields. I also included fine-grained data lookups to each item in the table. I created custom commands for this application to completely automate data population (since it was connected to an external REST API). 

Currently I have to upgrade this application to have a REST API to be used for any frontend frameworks, such as Angular or React. Since I have previous experience using Django Rest Framework, I decided to use the current data models I have and create serializers for them to allow for a quick development of the REST API. 

Since all the data is related to a particular user, I had to find a way to authenticate the user prior to providing data through the API. After some research I decided to go ahead and implement JSON Web Tokens ([jwt](https://jwt.io/)), since it seems to be industry standard and very secure. 

## What are JSON Web Tokens
JWT provide a way to securely transmit JSON objects with information between two parties. These JWT's can be signed with an HMAC algorithm ensuring security.

Taken from https://jwt.io:

JSON Web Tokens consist of three parts separated by dots (.), which are:
terr
- Header
- Payload
- Signature

Therefore, a JWT typically looks like the following.

`xxxxx.yyyyy.zzzzz`

and as an example: 

<img class="ui medium right spaced image" src="https://cdn.auth0.com/content/jwt/encoded-jwt3.png">

Decoding the JWT will provide data as a JSON object.

<img class="ui medium right spaced image" src="https://cdn.auth0.com/blog/legacy-app-auth/legacy-app-auth-5.png">

## How I'm using JWT's in my application
Since I am building a REST API with Django Rest Framework, I decided to look for packages that would possibly make my life easier to implement JWT. I gave [this](https://github.com/GetBlimp/django-rest-framework-jwt) a shot. Although the documentation isnt extremely helpful, it did help me get it up and running within an hour. The package is actually well built. It's super simple to use (from what I can see so far), and is really secure. 

In my urls.py I just added:

`url(r'^api-token-auth/', obtain_jwt_token)`

to my urlpatterns, and boom! tokens will automatically be generated based on their username and password and if there is a match to the built in (and secure) Django User models. 

The documentation didn't give too much information on usage, so I had to dig around to figure out how to use it. But when I figured it out, it was actually super simple.

In the ViewSet you simply add:

```
class InfoViewSet(viewsets.ModelViewSet):
   permissions_classes = (IsAuthenticated, )
   authentication_classes = (JSONWebTokenAuthentication, )
   serializer_class = InfoSerializer

   def get_queryset(self):
   return info_service.get_info(self.request.user)
```

As you can see in this snippet, you simply apply a permission class to the viewset to make sure that user is in the database, and is authenticated with the JWT. 

## Continuing on
I added these to all viewsets for all the API endpoints and everything seems to be working alright, so I will probably have to do somet testing and token refreshing functionalities.










