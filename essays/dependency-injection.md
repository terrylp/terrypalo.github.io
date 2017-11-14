---
layout: essay
type: essay
title: "An Extra Layer of Abstraction To Make Your Life Easier"
date: 2017-11-13
labels:
  - Angular
  - "Dependency Injection"
  - "Mock Services"
---

## Introduction
I've been working on an Angular project for the past month creating mock services to run the frontend application locally without having to connect a backend. I've written about my experiences with mock services in the past, but it occurred to me that I never spoke about dependency injection in general. Dependency, in my opinion, is a really important paradigm of software development and it can really save you a ton of time if you implement it correctly.

## Dependency Injection
Dependency injection is a paradigm of software development that creates loosely coupled dependencies to be shared across the application. It allows for another level of abstraction which allows for service objects, for instance, to be used by different components or modules in an application, so services don’t have to be recreated every time. 

<img class="ui medium centered image" src="http://s2.quickmeme.com/img/7a/7acc20814836b3ed1a4c9b6600479ec2dca67643180185bd8c62acaf23da8352.jpg">

For example with Angular:

animal-service.ts
```
...
@Injectable()
export class AnimalService {
	animals = ['Giraffe', 'Gorilla', 'Monkey'];

	public getAnimals() {
		return this.animals;
	}

	public addAnimal(animal) {
		this.animals.push(animal); 
	}
}
...
```

and in one component:

displayAnimals.ts
```
import { AnimalService } from '../services/animal-services'
...

@Component({
  selector: 'display-animals',
  templateUrl: 'displayAnimals.html',
  providers: [AnimalService]
})

export class DisplayAnimals {
	animalsToDisplay = [];

	constructor(animalservice: AnimalService) {
		this.animalsToDisplay = animalService.getAnimals();
	}
}
```

and in another component:

addAnimals.ts
```
import { AnimalService } from '../services/animal-services'
...

@Component({
  selector: 'add-animals',
  templateUrl: 'addAnimals.html',
  providers: [AnimalService]
})

export class AddAnimals {

	constructor(animalService: AnimalService) {}

	addAnimal(animal) { 
		this.animalService.addAnimal(animal);
	}
}
```

As you can see the first component only needs to use the getAnimals() function of the animals service, while the second component only needs to use the addAnimal() function. This benefit both components because it allows for functions that are scoped at a particular dataset to be grouped together while being able to be loosely coupled between multiple components.

## Problems I've ran into
While creating mock services, I decided to replace providers with their respective mock service provider, so you can simply just enable and disable mock service function by commenting out providers. The concept itself seems easy - just simply throw all the providers in `app.module.ts` where providers will be created globally for all components, but the issue I have is that there are some services that depend on others, so components do not load correctly. So, the quick solution I've taken is to just add providers for some of the services that may be redundant for others.

<img class="ui medium centered image" src="https://daveceddia.com/images/yo-dawg-imports.jpg">

## Other Thoughts
I'm still learning different paradigms of software development, so my knowledge of dependency injection, for example, is very limited. I think the only way to get a full idea of these concepts is to just simply continue to develop software.

<img class="ui medium centered image" src="http://braginteractive.com/wp-content/uploads/2015/12/meme-i-have-no-idea-what-i-am-doing.png">

(How I feel when I'm trying to learn something new)

 







