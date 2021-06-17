---
layout: post
title: "Self-signed Certificates for Plex Media Server"
category: sysadmin
---

Create key and certificate

Create PKCS12 certificate

Get ProcessedMachineIdentifier

    cat /config/Library/Application\ Support/Plex\ Media\ Server\Preferences.xml

Example: ProcessedMachineIdentifier="2cbc18598cd802a9d856dabdd52bf29b4r0e24gq"

Create private key using pem2plex.py

    wget https://raw.githubusercontent.com/sadsfae/misc-scripts/master/python/pem2plex.py

    python pem2plex.py plex.crt plex.key 2cbc18598cd802a9d856dabdd52bf29b4r0e24gq

This will generate a long hash. Save it we'll need it later.

    d145ed250dfbd97fbc6e27b40b9c1e9bc83e541b43696f6535cd08abfe7d7ff97f3022ef848f0a27a5d75083ef191dd3da970aeb237c8d2c67c6af834379674b

We now have certificate.p12 and the long hash (passphrase) above.

Install certificate in Plex

Login to Plex and go to Settings->Server->Network

Insert the path where you placed certificate.p12 i.e /etc/ssl/private/plex/certificate.p12

Insert the long hash on Custom certificate encryption key

Source: [How to Use Self-signed SSL Certificates for Plex Media Server](https://hobo.house/2016/11/11/how-to-use-self-signed-ssl-certificates-for-plex-media-server/) [archive](https://archive.fo/mMcFi)
