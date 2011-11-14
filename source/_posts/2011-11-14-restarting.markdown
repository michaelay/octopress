---
layout: post
title: "Restarting Pow"
date: 2011-11-14 16:31
comments: true
categories: RubyOnRails
author: Michael Au-Yeung
---
<p>
Pow is a zero configuration web server for ruby on rails development. 
You can download it from <a href="pow.cx">pow.cx</a>.
</p>
<p>
While it's easy to install, sometimes you will need to restart it to keep things working.
</p>
<p>
The easiest way is to do this under the rails app folder: 
</p>
``` sh 
~ michael$ touch tmp restart.txt 
```
<p>
The command restart the server. 
What if the pow itself does not respond at all and touching the restart.txt does not work? 
</p>
<p>
You can restart the service as follow: 
</p>
``` sh 
~ michael$ launchctl unload -Fw ~/Library/LaunchAgents/cx.pow.powd.plist
~ michael$ launchctl load -Fw ~/Library/LaunchAgents/cx.pow.powd.plist
```

