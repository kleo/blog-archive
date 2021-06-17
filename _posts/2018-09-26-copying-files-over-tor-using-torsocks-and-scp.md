---
layout: post
title: "Copying files over Tor using torsocks and scp"
category: notes
---

If you haven't setup a Tor service on machine follow the link below.

[Setting up Tor on your machine on Torproject.org](https://www.torproject.org/docs/debian.html.en)

[Setting up Tor hidden service](https://www.torproject.org/docs/tor-onion-service.html.en)

We'll take advantage on port forwarding your ssh port 22 using a Tor hidden service.

To copy files or directories over Tor we need to use `torsocks` to communicate with the remote machine.

For files

```
torsocks scp file kbeflo@hostname.onion:/home/kbeflo/
```

For directories

```
torsocks scp -r directory/ kbeflo@hostname.onion:/home/kbeflo/
```

The hidden service will show password prompt for your username and will copy the files after.

Note that you have to change the username and hostname on your side. As an example I used my username and placeholder hostname.onion.
