---
layout: post
title: "ActiveRecord - use include to optimize SQL query performance"
date: 2011-11-14 15:14
comments: true
categories: RubyOnRails ActiveRecord
---
<p>
Consider you have a model Post and a mode Comment, where a Post has multiple Comments. 
You DB has 10 Posts and 2000 Comments. 
Now you want to get the all Posts and all Comments. How many SQL is executed if you do the following?
</p>
``` ruby 
posts = Post.all
posts.each do |p| 
  p.comments   
end 
```
<p>
Rails execute 2010 SQL query for you. The code is easy to write, but not so fun to run on your webserver. 
Rails gets the id of the Post objects and use them in 2000 seperate SQL query to get their Comments. 
What about getting all the Comments all together when fetching the Post objects? 
The <em>include</em> method does exactly that. 
It tells Rails to run one additional SQL query to fetch all the Comments object after the SQL fetch a Post object. 
The code is as follow: 
</p>
``` ruby
Post.all(:include => :comments)
```
<p>
And this piece of code runs 20 SQL query instead of 2010 in the previous version. 
Yet another nice little thing to distinguish between software engineers and programmers.
</p>
