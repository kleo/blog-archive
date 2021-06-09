---
layout: post
slug: USB powered Xperia C5 Ultra
category: mobile
---

A little history on this phone

My parents bought me a Xperia C5 Ultra (E5553) phone while I was still studying at college, bought at around 2015. 

Since graduating battery died and I haven't replaced it ever since. 

Buying a manufactured battery for a very old phone would be at a terrible quality by then.

I rooted this phone before when it was still on Android 5 with bootloader unlocked. Sadly I messed it up badly so I had no choice but to use Xperia Companion to recover it.

Unrooted, bootloader locked, recovery mode lost. Well at least I still have a working phone.

---

Previously I modded this phone with 1 USB cable for power and another connected to its USB micro port for helping it boot and maintain being powered on.

![](/img/2021-04-02/1.jpg)

For reference I found on google the pinouts for my phone here [u2ugsm.com](http://www.u2ugsm.com/blog/sony-xperia-c5-ultra-battery-connector-terminal/)

Replace blue with green + (RX) and replace yellow with white - (TX)

![](/img/2021-04-02/2.png)

I attempted to do serial and power with 1 cable but it isn't enough, phone won't power on. I forgot to take a picture on that attempt :\

Next I used 2 cables, one for serial and one for power

![](/img/2021-04-02/3.jpg)

A closer look at my awful soldering skills

![](/img/2021-04-02/4.jpg)

Really happy with the outcome. I could do USB adb and use [scrcpy](https://github.com/Genymobile/scrcpy)!

![](/img/2021-04-02/5.jpg)

Streaming

![](/img/2021-04-02/6.jpg)

I'm salty on the support Sony did on this phone, Android support only up to Marshmallow and no wireless adb but still this phone still feels like brand new.

