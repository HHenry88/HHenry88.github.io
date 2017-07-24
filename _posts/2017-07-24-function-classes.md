---
layout: post
title:  "Functional Classes"
date: 2017-07-24 21:06:26 +0800
categories: Functional-Classes
---
This is a 3 parter where I talk about functional vs functional shared vs prototypal vs pseudoclassical class patterns.

What's a class?:
  A class is a construct that is capable of building a fleet of similar objects that all conform to some interface. Also called constructors. And what gets returned from these constructors is an instance.

It's like if we were making a clay doll. Instead of making it by hand each time we want to make a new doll, we could use a mould. Slap some clay into the mould, press the mould together, and voila, we have a new doll with a lot less effort than making it by hand alone.

That's basically what a constructor does, in Javascript it's just a function that returns an object with whichever properties we want. Let's have a constructor called Human:

```javascript
  var Human = function(name){
    var newHuman = {};
    newHuman.name = name;
    newHuman.numberOfEyes = 2;
    newHuman.numberOfFingers = 10;
    newHuman.hasHair = true;
    newHuman.speak = function(){
      console.log('Hello, my name is', newHuman.name);
    }

    return newHuman;
  }

  var henry = Human('Henry Han');
```
Here, we made a Human constructor using functional class pattern. Nothing tricky about this, we made a Human named "Henry Han" with 2 eyes, 10 fingers, and has hair. And has the ability to speak to say "Hello, my name is Henry Han". Let's go through the code using pseudo code:

```javascript
  //Declare a Human class (a normal function) that has a single argument: name
  var Human = function(name){
    //Initialize a newHuman object. This is where we'll save our human information
    var newHuman = {};

    //Our newHuman will have a property called name, with the value equal to the argument 'name'
    newHuman.name = name;

    //Our newHuman will have a property called numberOfEyes, with the value equal to 2
    newHuman.numberOfEyes = 2;

    //Our newHuman will have a property called numberOfFingers, with the value equal to 10
    newHuman.numberOfFingers = 10;

    //Our newHuman will have a property called hasHair, with the value equal to true.
    newHuman.hasHair = true;

    //Our newHuman will have a method called speak, that console logs "Hello, my name is _____"
    newHuman.speak = function(){
      console.log('Hello, my name is', newHuman.name);
    }

    //We want our Human function to return/output a human. so we need to return our newHuman;
    return newHuman;
  }

  //We want to make a Human, named "Henry Han", and save it to the variable henry.
  var henry = Human('Henry Han');
```

So that's all functional class pattern is. Just using a normal function that outputs an object. There are pros and cons to the functional class pattern:

Pros:
1. Easy to read
2. Most intuitive of the 4 patterns

Cons:
1. A lot of syntax
2. Methods are duplicated each time a new instance is made.

Next we'll move onto functional shared patterns where it'll away our second con and methods will no longer be duplicated.
