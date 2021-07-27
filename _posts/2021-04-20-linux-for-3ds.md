---
layout: post
title: "Linux for 3DS"
category: github
---

Previous efforts by Sergi Granell ([xerpi](https://github.com/xerpi)) on [Linux for the 3DS](https://gbatemp.net/threads/release-linux-for-the-3ds.407187/) is now continued at [Linux for 3DS](https://github.com/linux-3ds). I discovered them on this [Reddit post](https://old.reddit.com/r/3dshacks/comments/mocfod/want_to_learn_how_to_load_linux_on_your_3ds/).

[Nick Desaulniers](https://github.com/nickdesaulniers) [stream on Twitch](https://www.twitch.tv/videos/983044002)[^1] has showcased the current progress and future plans for Linux for 3DS.

I made my share of helping the team out by providing a Dockerfile for settting up a build environment. [#15](https://github.com/linux-3ds/firm_linux_loader/pull/15), [#8](https://github.com/linux-3ds/arm9linuxfw/pull/8)

I also created automated builds with Github Actions so that every time a push is made to their repositories, Github Actions runs the build and automatically uploads the binaries to Releases as development builds. [#11](https://github.com/linux-3ds/arm9linuxfw/pull/11), [#20](https://github.com/linux-3ds/firm_linux_loader/pull/20), [#37](https://github.com/linux-3ds/linux/pull/37)

![](/img/2021-04-20/1.jpg)

Everything is just amazing

![](/img/2021-04-20/2.jpg)

Uploaded [Building Linux for the Nintendo 3DS](https://youtu.be/mTo8yb6q4Lw) stream to YouTube at 2021-06-17

[^1]: [https://www.twitch.tv/ndesaulniers](https://www.twitch.tv/ndesaulniers)
