---
layout: post
title: "Rails force SSL"
date: 2012-01-03 15:21
comments: true
categories: RubyOnRails SSL
author: Michael Au-Yeung
---
<p>
Staring rails 3, we shall avoid using ssl_requirement GEM, as the GEM does not work very well on heroku. 
Sometimes the HTTPS page is redirected and the URL params are lost. 

To fix this, force using HTTPS in config/routes.rb as follow: 

``` config/routes.rb 
  resources :accounts,
            :constraints => { :protocol => 'https' } do 
  # ... 
  end 
```

You can also use scope. 
</p>
