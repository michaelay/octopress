---
layout: post
title: "Javascript private variable through closure"
date: 2011-11-16 12:11
comments: true
categories: Javascript
author: Michael Au-Yeung
---
Defining Javascript class private instance variable
Example: 
``` javascript 
function MyClass(a) { // constructor
  this.getA = function() { return a; } 
}

MyClass.prototype.myFunc = function() { 
  return this.getA() + 1000; // do something with a 
}  
``` 
