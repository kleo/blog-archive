---
layout: post
title: "Powershell Windows 10 update"
category: sysadmin
---

Windows 10 upgrade woes

Start powershell as admin with unrestricted script policy

	powershell -executionpolicy unrestricted

Install windows update powershell module

	install-module pswindowsupdate

Get updates available for your pc

	get-windowsupdate

Install updates available

	install-windowsupdate

Or

Get updates and automatically install accept and reboot pc

	get-windowsupdate -install -acceptall -autoreboot

One liner

	powershell -executionpolicy unrestricted -command "install-packageprovider -name nuget -force -verbose; install-module pswindowsupdate -force -verbose; get-windowsupdate -install -acceptall -autoreboot -verbose"

Note:

Import module before `get-windowsupdate` if pswindowsupdate is already installed

	import-module pswindowsupdate

Update 2021-07-22

Specify TLS 1.2 for the .net Security protocol

    powershell -executionpolicy unrestricted -command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; install-packageprovider -name nuget -force -verbose; install-module pswindowsupdate -force -verbose; get-windowsupdate -install -acceptall -autoreboot -verbose"

References:

[https://www.altaro.com/msp-dojo/powershell-windows-updates](https://www.altaro.com/msp-dojo/powershell-windows-updates)

[https://superuser.com/questions/462425/can-i-get-more-information-on-what-windows-update-is-doing](https://superuser.com/questions/462425/can-i-get-more-information-on-what-windows-update-is-doing)

[https://stackoverflow.com/a/65207763](https://stackoverflow.com/a/65207763)
