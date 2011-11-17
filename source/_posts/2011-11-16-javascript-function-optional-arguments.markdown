---
layout: post
title: "Javascript function optional arguments"
date: 2011-11-16 11:21
comments: true
categories: Javascript
author: Michael Au-Yeung
---
Simple example: 
``` javascript 
function foo(a, /* optional */ b) { 
  b = b || []; // returns b if b is defined and non-null, 
               // even if b is empty.
} 
```
