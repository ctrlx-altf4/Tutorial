---
title: useState-basics
template: post
slug: useState-basic
draft: true
date: "2020-09-05"
description:
cover: ./.jpeg
category: react
tags:
  - react
  - hook
  - useState
---

# A brief intro to states in react

Even if you're an experienced react developer, you might have found yourself stumbling across the proper management of state. After all react itself is a statement management library ( as said by kent c dodds). Everything that we do in react eventally revolves around handling state and manipulating them. So, when you are starting with react, it's high time you realize all through out your career as a react developer you will be dealing with state management and render optimization that comes along with it.

## Structure of `useState` hook

<br/>

For now, lets start small. Do you know about array destructuring in javascript?? If not checkout `this article` that I've previously written as a part of es6 tutorial series.

Basically here is a small example:

```javascript
// Here I have just declare an array with two strings.
const state = ["this is state variable", "this is set State function"];

// without destructuring;
const x = state;

console.log(x[0]); // "this is state variable"
console.log(x[1]); // "this is set State function"

// With array destructuring;

const [firstValue, secondValue] = state;

console.log(firstValue); // "this is state variable"
console.log(secondValue); // "this is set State function"
```

I hope you get the gist. Now why am I talking about array destructuring? If you have tinkering on react with hooks for a while, then you have obviously come across this syntax:

```javascript
const [state, setState] = useState();
```

You might have been using this without understanding why it is done like that. So, Lets break the above expression. The `useState` is just a fancy way of writing a hook that returns an array. **Remember it's compulsory to add prefix "use" in function of react if you are building a custom hook**

`useState` is just a function that returns an array. The first element of the array is the state while the second element of the array is a function that sets the state.

so simply, what we could have done was:

```javascript
cosnt stateArray = useState();

// without array destructuring
const state = stateArray[0];
const setState = statearray[1];

//with array desctructing
// This is exactly same as above
const [state,setState] = useState()

```

Phew!! I hope you got that.

## Initialization

Now let's see why initializing state is different than initializing a random variable.

Open up your `create-react-app` environment. Go to you `app.js` file and copy the code below:

```javascript
import React from "react";

const App = () => {
  const [state, setState] = useState(0);
  let count = 0;

  console.log("count", count);
  console.log("state", state);

  return (
    <button
      onClick={() => {
        count++;
        setState(state + 1);
      }}
    >
      Click me
    </button>
  );
};
```

> The code above simply displays a button which when clicks changes the `state` and also changes the count variable.

Since state simply stores some data, it may seem irrelevant to make use of `useState` to get a `state` variable to store the data and a function to set that state. I mean, we could simply use a js variable to store a data:

```javascript
let count = 0;
```

but somehow this doesn't work. Why? Did you run the above react code?? Did you see the difference between the console output of `count` and `state`? Do you know, why the answer varies??
