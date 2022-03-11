---
layout: post
title: "Termux Selfhost Android 5 and 6 Legacy Packages"
category: mobile
---

Termux Selfhost Android 5 and 6 Legacy Packages

Termux has long dropped support for Android 5 and 6 but still have provided legacy packages on termux.net. [^1]

Here's a guide on setting up a local mirror

Download the packages archive termux-repositories-legacy-24.12.2019.tar [^2]

```
# on termux 0.75 fdroid archive

export EDITOR=vi
apt edit-sources

# configure local mirror
deb http://192.168.1.250/termux-packages stable main

# comment game.list/science.list sources

vi ../usr/etc/apt/sources.list.d/game.list
vi ../usr/etc/apt/sources.list.d/science.list

# on computer
# extract termux-repositories-legacy-24.12.2019.tar
cd termux-repositories-legacy/webroot
sudo python3 -m http.server --bind 0.0.0.0 80

# on termux
pkg update
pkg install openssh
```

[^1]: [End of android-5/6 (termux.net) support on 2020-01-01](https://github.com/termux/termux-packages/issues/4467)
[^2]: [archive.org Termux app and packages for legacy Android OS](https://archive.org/details/termux-repositories-legacy)