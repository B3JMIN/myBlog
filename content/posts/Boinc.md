+++
title = "Raspberry Pi"
date = "2020-04-03"
author = "Benjamin Cai"
description = "Blog for playing with Raspberry Pi"
showFullContent = false
+++


# Use Raspberry Pi for exploring the outer Space

I bought a Raspberry Pi last week and after I finish all the downloading and environment setting, I decide to make some interesting software on that and play some fun stuff.

{{<figure src="/static/img/bonic.png" alt="bonic picture" position='center' style='border-radius:8px;' >}}

First I install [seti@home](https://setiathome.berkeley.edu/) on Raspberry Pi:
```html
  sudo apt-get install bonic
  sudo apt-get install bonic-client
```
Then I just follow this [instruction](https://pimylifeup.com/raspberry-pi-boinc/) to setup it
However, I found it takes more than 20 hours for it to compute 1 task...
so I decided to make more useful server...

# Make a Samba file server
There is a long story why i decide to make this...

My roommate Scott is now working in a startup doing some web develop, what he did mostly is ```html npm build && npm start```. On a normal Wednesday he asked me to run that command for him since his computer cannot run ```html npm build ``` :) I literally don't believe that so we just reinstall npm and node for his windows laptop, but that does nothing.

He decided to send me all the file, we tried to use Wechat and email, but he found that Wechat cannot do that big file transfer and I think using email for all the node packages is a stupid thing..

why not using the Pi?
I installed samba server on that and figure out the ip address, we connect both to the server but we found the speed depends on wifi speed... so it takes 50 mins

here is a picture when I connect my phone to the server:
{{< figure src="/static/img/iphoneShare.png" alt="iphone Share" position="left" style="border-radius:8px;" >}}
I like the server idea even it failed with this speed... :P
