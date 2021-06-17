---
layout: post
title: "Router Privileged Backdoor Login"
category: routers
---

Tired of always asking for the WiFi password? Well here in the Philippines, routers come with privileged backdoor login, where we can access the router's configuration, where we can set the WiFi network name(SSID) or even change the WiFi password, or just view the current configuration, such as the WiFi password in plain text.

The vulnerability exists between common routers used in the Philippines, these are the **Globe PROLiNK H5004NK** and the **PLDT BaudTec RN243R4-2T2R-A6**.

### Physical access attack

Physical access is a term in computer security that refers to the ability of people to physically gain access to a computer system. The best network software security measures can be rendered useless if you fail to physically protect your systems.

### Scenario

We will need to have physical access to a computer already connected to the network. This can commonly be found on homes, internet cafes, and workplace networks where the router isn't secured behind a firewall.

They come with an open ssh service on port 22, with default usernames and passwords. An added bonus is that these accounts' passwords cannot be changed and cannot be removed, so we can use them to login to any of these routers at any time we want.

### Globe PROLiNK H5004NK

![](/img/2017-08-30/01.png)

XXXX being the last 4 characters of the device's MAC address.

### PLDT BaudTec RN243R4-2T2R-A6

![](/img/2017-08-30/02.png)

XXXX being the last 4 characters of the device's MAC address.

### Accessing the the router's command line interface

You can find the router's IP address on Windows using cmd, then entering `ipconfig` command, normally this would be the default gateway on most unsecured networks.

![](/img/2017-08-30/03.png)

To identify the router's MAC address you can simply go to the router's IP address and access it's web interface and view all it's info without even logging in.

![](/img/2017-08-30/04.png)

We will need an ssh client to connect to the router, we'll be using [PuTTY](http://putty.org/) an ssh client for Windows as an example.

Enter the gateway IP address (e.g 192.168.254.254) and ssh default port 22 and open connection.

![](/img/2017-08-30/05.png)

Now we can login to ssh using the privileged backdoor username and password and view the WiFi password by entering shell using `sh` command, then `show wlan config` command.

![](/img/2017-08-30/06.png)

We'll get a list of the router's wireless configuration, now look for these entries,

![](/img/2017-08-30/07.png)

WLAN SSID is our WiFi access point name, and WLAN WPA_PSK is the WiFi password.

There you have it, the WiFi password in plain text. Have fun~
