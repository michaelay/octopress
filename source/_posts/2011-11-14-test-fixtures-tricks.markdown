---
layout: post
title: "Test fixtures tricks"
date: 2011-11-14 15:03
comments: true
categories: RubyOnRails
author: Michael Au-Yeung
---
<p>
Often we have model classes using serialized data fields. 
This is how I write the YML fixture test data:
</p>
``` ruby Test fixture YML example for serialized array, serialized hash, and datetime
one:
  id: 100
  some_hash_serialized: <%= { :profile_image_url => 'http://....png' }.to_yaml.inspect %>
  some_array_serialized: <%= [ 'hello', 'world' ].to_yaml.inspect %>
  some_datetime: <%= first_occurred_at: <%= 10.days.ago.to_s(:db) %>
```
