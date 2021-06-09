---
layout: post
slug: PLDT Home Fiber router firmware and files
category: routers
---

Continuation for hacking the PLDT FIBR AN5506-04-FA router RP2616

- [Hidden urls](/pldt-home-fiber-router-hacking)
- [Console access](/pldt-home-fiber-router-console-access)
- [Router firmware and files](#)
- [Admin access](/pldt-home-fiber-web-interface-admin-access)

## Firmware and files

Now we have console access to the router, we can freely dump files from the device.

## Preparing flashdrive

Format a flashdrive to a FAT32 file system

## Dump

Boot up the router first then wait for the third prompt and press Ctrl+C

After that plugin the flashdrive

We need to remount the flashdrive so that we can properly copy files from the router 

`umount /dev/sda1`

`mount /dev/sda1 /dev/shm/usb/media/sda1`

Then copy the files using `cp`, for example

`cp uImage /dev/shm/usb/media/sda1`

`cp proc/cpuinfo /dev/shm/usb/media/sda1`

`cp -r fhcfg/ /dev/shm/usb/media/sda1`

Preview on the console

<a href="https://asciinema.org/a/FxbkBVUXEEL5jfmcoWw8OTmAi" target="_blank"><img src="https://asciinema.org/a/FxbkBVUXEEL5jfmcoWw8OTmAi.png"></a>

## Interesting info found on the router

	Linux version `/proc/version`

	Linux version 2.6.34.10 (root@Fedora-server) (gcc version 4.4.6 (crosstool-NG 1.13.2 - hsan-5115) ) #1 SMP PREEMPT Mon Sep 11 15:03:15 CST 2017

	cpuinfo found at `/proc/cpuinfo`

	Processor	: ARMv7 Processor rev 1 (v7l)
	processor	: 0
	BogoMIPS	: 1395.91

	processor	: 1
	BogoMIPS	: 1395.91

	Features	: swp half thumb fastmult edsp 
	CPU implementer	: 0x41
	CPU architecture: 7
	CPU variant	: 0x4
	CPU part	: 0xc09
	CPU revision	: 1

	Hardware	: sd5115
	Revision	: 0000
	Serial		: 0000000000000000

WiFi configuration found at `/fhcfg/fh_wifi/wifictl_2g.cfg` and `/fhcfg/fh_wifi/wifictl_5g.cfg`

Random default WiFi password stored at `/fhcfg/fh_wifi/wifipskkey.cfg`

Also found all the hidden pages that are available on the web interface. I will include them on the Gist found on [Hidden urls](/pldt-home-fiber-router-hacking)

## Acknowledgements

[FiberHome AN5506-02-F router hack](https://hackcorrelation.blogspot.com/2017/07/fiberhome-an5506-02-f-router-hack.html) by Ligius

[Practical Reverse Engineering](http://jcjc-dev.com/2016/04/08/reversing-huawei-router-1-find-uart/) awesome writeup by Juan Carlos Jimenez
