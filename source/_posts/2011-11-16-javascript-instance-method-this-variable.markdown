---
layout: post
title: "Javascript instance method this variable"
date: 2011-11-16 12:05
comments: true
categories: Javascript
author: Michael Au-Yeung
---
In Javascript class instance method, you must use the <em>this</em> variable to access instance variables. 
For instance: 
``` javascript Javascript version
return this.foo; 
```
as oppose to in C++: 
``` c++ C++ version
return foo;
```
One way to get around with using this for every instance variable is as follow: 
``` javascript 
MyClass.prototype.myFunc = function() {
  with(this) { 
    return foo;
  } 
} 
```
