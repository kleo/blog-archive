---
layout: post
slug: Aztech Globe DSL5068EN-1T1R WiFi Password Telnet
category: routers
---

Aztech Globe DSL5068EN-1T1R WiFi Password using telnet

Using [PuTTY](https://www.putty.org/) or another telnet client

Connect to the router's telnet service on port 23 at 192.168.254.254, using..

<b>Username:</b> admin

<b>Password:</b> 3UJUh2VemEfUtesEchEC2d2e

Limited commands are available so we can't find and grep the WiFi password easily

Lucky for you I already got the file path

`cat /tmp/var/romfile.cfg`

Scroll up look for this block

```
<Entry0 EnableSSID="1" SSID="redacted" HideSSID="0"
AuthMode="WPAPSK" EncrypType="TKIPAES" RADIUS_Server="192.168.7.203"
RADIUS_Port="1812" RADIUS_Key="12345678" BAK_RADIUS_Server=""
BAK_RADIUS_Port="" BAK_RADIUS_Key="" AccessPolicy="0" WMM="0" HT_MCS="33"
WPSConfStatus="2" WPSMode="0" WscDefaultSSID1="Ralink_AP" WPSKeyASCII="8"
WPSConfMode="0" IgmpSnEn="0" KeyPassphrase="" RekeyInterval="10"
WEPAuthType="WEPAuto" HT_RATE="0" NoForwarding="0"
WPAPSK="lamepassword123" MaxStaNum="16" />
```

and find the WiFi password `WPAPSK="lamepassword123"`

Don't forget to throw away the router. Have fun~
