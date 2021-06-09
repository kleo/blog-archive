---
layout: post
slug: OpenWrt self signed certificate
category: routers
---

Secure your connection to your openwrt router on lan using a self signed certificate.

Setup dnsmasq to point to your router i.e openwrt.home to 192.168.1.x

Generate a certificate and key using openssl, I'll be using xca.

After that install luci-ssl

    opkg install luci-ssl

On xca export certificate as a binary DER encoded file, openwrt.home.cer

and export key as a unencrypted private key in binary DER format.

Copy files to your router

Rename openwrt.home.cer to uhttpd.crt

Rename oepnwrt.home.der to uhttpd.key

Move uhttpd.crt and uhttpd.key to /etc/

Restart uhttpd

    /etc/init.d/uhttpd restart

Reload page

todo: create xca usage guide

references:

[https://openwrt.org/docs/guide-user/services/webserver/uhttpd#https_enable_and_certificate_settings_and_creation](https://openwrt.org/docs/guide-user/services/webserver/uhttpd#https_enable_and_certificate_settings_and_creation)

xca [https://hohnstaedt.de/xca/](https://hohnstaedt.de/xca/)

