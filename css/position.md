---
title: position-css
template: post
slug: position-css
draft: true
dateStarted: "2021-07-19",
lastEditedOn: ""
description:
cover: ./.jpeg
category: css
tags:
  - css
  - absolute
  - relative
  - fixed
  - sticky
  - position
---

# A Brief Intro to positioning in css

There are five types of positions in css till now:

1. static
2. fixed
3. relative
4. absolute
5. sticky

Positioning can be a tricky concept, and as you dive deeper on positiiong you start to find one position being directly or indirectly related to another and somehow when manipulating positions other properties in css doesn't seem to work. It is complicated. I'll try my best to explain them and how they affect other properties.

## Flow of the document

//TODO

You've to got to understand how each elements are placed on the DOM by default. You should be able to identify `block` level element and `inline` element

### position:static;

- default
- no affects by offsets
- block and inline has different properties

notes:

1. talk about offset : top, bottom, left and right
2. absolute and its relation to relative (parent element)
3. fixed and its relation to viewport
4. z Index on overlap
5. float and why it sometimes make no sense
6. sticky and why it fails on scrolling (in some cases??)
