---
layout: essay
type: essay
title: "API Testing Made Easy"
date: 2017-10-09
labels:
  - Django
  - DRF
  - "Testing"
---

## Introduction
On another week with Django Rest Framework and creating the _perfect_ API, I decided to dedicate this week to creating tests for every feature and functionality of the API. 

Luckily, Django provides a way to easily test your API along with built in functions that expedite the whole process. The best part is that there is extended support for Django Rest Framework as well!

<img class="ui medium centered image" src="../images/sw-unit-tests.jpg">

## Testing With Django Rest Framework
When you test your API with Django Rest Framework, you can simply just start creating your test in the test.py files that are created when the application is created. Along with that, you can import an API testing library that is built into django already with `APITestCase`. You can then create a testing parent class along with functions that start with `test_`. When you actually start the tests you simply just type `python manage.py test`, and boom! All definitions that start with `test_` will be ran.

The Django Rest Framework APITestCase libarary will also allow you to directly test your API.

For instance:

```
...
response = self.client.post(
    "/api/data/",
    {'field_one': 'data_one',
        'field_two': 'data_two'},
    HTTP_AUTHORIZATION='JWT {}'.format(token))

response = self.assertEqual(response.status_code, 201, "Post Passed")
...

```

this little snippet of code will simply create a post request on /api/data/ with the body of 'field_one' and 'field_two'. As soon as it creates the request, then you can assert the known outcome to ensure your test passed. What is really cool is that the data is not stored into your database, but instead its cached temporarily until the tests complete, then it will dump it.

### Small Issue
One of the main issues that I had was trying to get the JSON Web Token in every single test. Since there are no global variables, the token has to be requested on every single test. 

To solve this issue, I just ended up creating a service that would create a new token, so all you would have to do is call a get_token function, and in one line, it would return the results.



