---
title: class Vs idd
template: post
slug: class-vs-id
draft: true
startedOn: "2021-07-20",
lastEditedOn: "2021-07-20"
description:
cover: ./.jpeg
category: css
tags:
  - css
  - styles
  - class
  - id
  - class vs id
---

# class vs id in css

If you are using class and id only for styling then there is no any difference between class and id. If you have been googling for a while on the difference,you might have read ids are unique in a page while classes are can be used multiple times. I agree on your findings, id are supposed to be unique in a page while classes can be used multiple times in several elements. But neither html nor css nor javascript validate the uniqueness of id, so that must be confusing.

Run all the follwing HTML, CSS and JS in [codepen](https://codepen.io/pen/)

Consider the following HTML & CSS

HTML

```html
<div class="red">I am from first class div</div>
<div class="red">I am from second class div</div>
<div id="blue">I am from first id div</div>
<div id="blue">I am from second id div</div>
```

CSS

```css
.red {
  background: red;
}
#blue {
  background: blue;
}
```

### Difference 1

> Only difference while applying styles is how they are represented in `css`. Syntax for class selector is `.class` while for id selector `#id`. We use (.) followed by the class name to apply styles to class while (#) followed by id.

Now lets get into javascript for a while

```javascript
const id = document.getElementById("blue");
const className = document.getElementsByClassName("red");

console.log("id", id);
console.log("class", className);
```

Observe carefully for id we have getElementById without `s` while for class we have getElementsByClassName with `s` clearly indicating we can get multiple with with a classname but only one element with an id.

### Difference 2

> The output of id will the first div with the id "blue" all other divs with "blue" are ignored. While the output of class will be all the div with the class "red". Here the concept of uniqueness is important. Since we can clearly see that only one div with the id blue is found by javascript and all other div with id blue are ignored.

Consider the follwing HTML & CSS

HTML

```HTML
  <div class="red" id="blue">
    I am from red class and blue id
  </div>
```

CSS

```css
.red {
  background: red;
}
#blue {
  background: blue;
}
```

### Difference 3

> The background of the div will be blue. When both id and class are used for same css property on the same element then the property of id will be given priority

Consider the following HTML & CSS

HTML

```HTML
<div class="red" id="navbar">
  I am from red block
</div>
<div class="blue" id="contact">
  I am from blue block
</div>

<div class="green" id="footer">
    I am from green block
</div>
```

CSS

```css
.red {
  background: red;
  width: 100vw;
  height: 600px;
}
.blue {
  background: blue;
  width: 100vw;
  height: 600px;
}
.green {
  background: green;
  width: 100vw;
  height: 600px;
}
```

The HTML and CSS above will display red , blue and green block each of height 600px. Say you are running your HTMl and css on url: `localhost:8000`. Now if you add `#footer` on the url, the browser will scroll down to the div with footer id.

If you access this url:
`localhost:8000#footer` then the browser will scroll down the footer div whose background color is green.

You might be finding it difficult to simulate this on codepen. but trust me on this. You can run a live server on your device and try it on your local machine if you can set it up. If not, trust me on this, when have I ever lied (to you)?

### Difference 4

> You can access the section of the html by adding `#idName` on the url while this feature isn't available to class.

In the above css you can see tha we've been repeating `width:100vw; height:600px;` lets separate that to a different class with the code below:

HTML

```HTML
<div class="red section" id="navbar">
  I am from red block
</div>
<div class="blue section" id="contact">
  I am from blue block
</div>

<div class="green section" id="footer">
    I am from green block
</div>
```

CSS

```css
.red {
  background: red;
}
.blue {
  background: blue;
}
.green {
  background: green;
}
.section {
  width: 100vw;
  height: 600px;
}
```

In the HTML we've added two classnames each separated by a space. The first classname (red, blue or green) is providing the color while the next class (section) is providing the measurement of the `div`.

### Difference 5

> We can add multiple class names to same element but one element can have only one id.
