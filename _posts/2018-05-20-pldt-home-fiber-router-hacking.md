---
layout: post
slug: PLDT Home Fiber router hacking
category: routers
---

A walkthrough on my current progress on hacking the PLDT FIBR AN5506-04-FA router RP2616.

- [Hidden urls](#)
- [Console access](/pldt-home-fiber-router-console-access)
- [Router firmware and files](/pldt-home-fiber-router-firmware-and-files)
- [Admin access](/pldt-home-fiber-web-interface-admin-access)

## Hidden urls - looking for advanced settings on the web interface

After a long wait for the ISP to install our new fiber internet connection, finally I can enjoy that 50 Mbps speed at home. The technicians finished setting up the fiber connection, router and phone. They head on home.


Accessed the web interface on my computer at **192.168.1.1** with the default username **admin** and password **1234**. Initial setup was a breeze, asking for a new admin password, WiFi password for 2.4GHz and 5GHz.

While all is well first thing I noticed is the very limited settings on its web interface, bummer.

## Scanning for urls

So to try a few things, I booted up [Kali Linux](https://www.kali.org/) and went on to use `dirb`, a web content scanner. Basically it looks for existing (and/or hidden) Web Objects.

![](/img/2018-05-20/01.png)

Now looking at the urls, they end with *.asp*, let's try adding an option to dirb to end with *.asp* file extension.

![](/img/2018-05-20/02.png)

While I found just a couple of additional hidden urls, these won't be enough.

## All hope is not lost

Luckily I found a similar router page for the AN5506-04-FA router. You can find the page at [Hackcorrelation](https://hackcorrelation.blogspot.com/2017/07/fiberhome-an5506-02-f-router-hack.html). Mirrors [1](https://archive.fo/uWVbx) [2](https://web.archive.org/web/20180429125804/https://hackcorrelation.blogspot.com/2017/07/fiberhome-an5506-02-f-router-hack.html)

The article provided me file urls such as `http://192.168.1.1/menu/sfu/ph_pldt/hisi5116/voip_dualwifi/sip/1.xml` which contained more hidden urls on the router.

Now I can do so much more, like **port forwarding** and increasing **WiFi power to 200%**!

I listed all the hidden urls and files at [https://github.com/bkspc/fiberhomesuperadmin/](https://github.com/bkspc/fiberhomesuperadmin/)

#### [Console access](/pldt-home-fiber-router-console-access)
