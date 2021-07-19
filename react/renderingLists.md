---
title: rendering-lists
template: post
slug: rendering-lists
draft: true
dateStarted: "2021-07-19"
description:
cover: ./.jpeg
category: react
tags:
  - react
  - map
  - key
  - list
  - array
---

## `map` vs `forEach` method of react;

Do you know the difference between `map` and `forEach` method of javascript?

```javascript
const arrayOfVariants = [1, 2, 3, 4, 5];

const x = arrayOfVariants.map((each) => each * 2);

const y = arrayOfVariants.forEach((each) => each * 2);

console.log("map method", x); // [2,4,6,8,10]
console.log("forEach method", y); // undefined
```

The output of `map` method is an array while forEach method doesn't have any output. If you want to know more about `map` vs `forEach` you can look at my article _here_.

For this article, it's enough to understand the output of each method. Since, the output of a `map` method of an array is an array while `forEach` doesn't have any output. This clear distinction between these two methods helps in understanding why `map` is used extensively in react.

## Rendering elements in react

Copy the following code in your `create-react-app` environment and add it in your `app.js` file.

```javascript
import React from "react";

const App = () => {
  const number = 123;
  const string = "I am a string";
  const array = [1, 2, 3, 4, 5];
  return (
    <div>
      {number}
      {string}
      {array}
    </div>
  );
};
export default App;
```

We can use javacript expression by wrapping it in curly `"{}"` braces in _JSX_.So, You should see that react will successfully display the value of string, number and an array on the browser.

For now we'll not be going into what datatypes cannot be rendered by react, to know more about these _read here_. `Mind you, Objects cannot be rendered by react`.

What I want you to focus in this part, is that along with strings and numbers we can also render an array within in JSX. So why is that important? Lets combine our knowledge about the previous section on output of `map` method with the array being rendered by react.

```jsx
import React from "react";

const App = () => {
  const number = 123;
  const string = "I am a string";
  const array = [1, 2, 3, 4, 5];
  const mappedArray = array.map((each) => each * 2);
  console.log("mappedArray", mappedArray); //[2,4,6,8,10]
  return (
    <div>
      {number}
      {string}
      {array}
      <p>mapped Array: {mappedArray}</p>
      <p>mapped Expression: {array.map((each) => each * 2)} </p>
    </div>
  );
};

export default App;
```

If you run the above code, you should see the mappedArray being rendered on the screen using both the `variable` mappedArray and the expression `array.map((eeach=>each*2))`. Since as mentioned in the first section the ouput of `map` method is an array and as mentioned in the second second array is a valid react child.

## `key` in array rendering.

Okay! Lets see another example.

```jsx
import React from "react";

const App = () => {
  const names = [
    "Jordan Walke",
    "Dan Abramov",
    "Kent C. Dodds",
    "Tanner Linsley",
  ];

  return (
    <div>
      {names.map((each) => (
        <p>{each}</p>
      ))}
    </div>
  );
};

export default App;
```

This might seem a bit weird for you. Here we have used a map method on `names` array and returned `jsx element` i.e. `<p>{each}</p>`. It should be clear by now that the output of the `map` expression is an array of jsx element.

```jsx
{
  names.map((each) => <p>{each}</p>);
}

// output of above expression
<div>
  <p>Jordan Walke</p>
  <p>Dan Abramov </p>
  <p>Kent C. Dodds </p>
  <p>Tanner Linsley </p>
</div>;
```

Now you should be seeing names being displayed on the browser. If you inspect the element (`how?`) you should be able to see each name being wrapped by `p` tag like the output mentioned above.

But in the `console tab` a warning message like the one below appears. Do you know why's that??

Warning: Each child in a list should have a unique "key" prop.

-- To be continued

//TODO

Questions?

1. What is jsx Element
2. Object can't be a valid react child
3. array methods
4. `{}` in react
