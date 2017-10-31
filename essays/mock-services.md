---
layout: essay
type: essay
title: "Mock Services: Saving You Time and Money"
date: 2017-10-30
labels:
  - Angular
  - "Mock Services"
  - "Testing"
---

## Introduction
The last two weeks I was assigned an Angular project and my responsibility has been creating mock services for the current API that the application uses. This project relies on a REST API to deliver data, which must be connected to a database. Because of this, there has been a slight bottleneck in development because any time we would like to test a newly implemented feature we would have to build the project for production then push it to our individual development instance (which can take atleast 2 minutes every single time). As you can see, this can be a hassle to try and develop something simple.

<img class="ui medium centered image" src="https://media.giphy.com/media/88EvfARM1YaCQ/giphy.gif">

## The Solution: Mock Services
Mock services are essentially functions that provide static responses that you would normally get if you were to create a request on a live REST API. This is incredibly useful because it can provide a simple way to test frontend development and features with a sample set of data without creating a whole backend for it.

### Creating a Mock Service
Creating a mock service is really straightforward. You simply create an exact copy of what the normal service has, except you provide only static data instead of making an actual http request.

Example:

real_service.ts
```
...
@Injectable()
export class SampleService {
	private BASE_URL = 'http://test.api.com/'

	constructor(public http: Http) {}

	getAnimals() {
		return this.http.get(this.BASE_URL + '/animals/')
	}
}
...

```
and say, in this case it would return something like: 
```
animals = `{
	"results" : [
		"kangaroo", 
		"chicken", 
		"pig"
	]
}`
```


mock_service.ts
```
...
@Injectable()
export class MockSampleService {

	getAnimals() {
		animals = `{
			"results" : [
				"kangaroo", 
				"chicken", 
				"pig"
			]
		}`
		return Observable.of(animals)
	}
}
...

```

As you can see, both services have the same function name and return an observable, so they can be used interchangeably on the receiving end as long as you change the names and providers.

<img class="ui medium centered image" src="http://www.reactiongifs.com/r/2013/10/woah.gif">


### Downside
One of the downsides to mock services is that they will constantly need to be updated if there are any updates to the live backend. This can be a pain to maintain if there are a ton of relational objects as well, so you would need to make sure your static data is coherent and maintains consistency even when upgrading.






