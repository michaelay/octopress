---
layout: post
title: "Javascript function properties"
date: 2011-11-16 11:28
comments: true
categories: Javascript
author: Michael Au-Yeung
---
<p>
Sometimes you need variable in a function to persist across invocations. 
You can always define global variable to do that. However, that clusters up the namespace. 
</p>
<p>
A better way to do that is to define a function property accessible only to that particular function.
Example:  
</p>
``` javascript 
someFunction.counter = 0; 

function someFunction() { 
  return someFunction.counter; 
  // the counter is like a static function variable in C
} 
```
