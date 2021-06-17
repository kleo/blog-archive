---
layout: post
title: "Sony Xperia C5 Ultra mtk-su testing"
category: blog
---

google "latest rooting methods github android" at around 6 in the morning

2nd result [JunioJsv/mtk-easy-su](https://github.com/JunioJsv/mtk-easy-su)

Now I have found out that my old phone is vulnerable to CVE-2020-0069 discovered by Diplomatic from XDA[^1] [^2]

Check Sony Xperia C5 Ultra specs[^3]

Chipset Mediatek MT6752 (28 nm) matches with mtk-su compatible chipsets

---

Running mtk-su

```
adb push arm64/mtk-su /data/local/tmp
adb shell
cd /data/local/tmp
shell@E5553:/data/local/tmp $ chmod 755 mtk-su
arm64/mtk-su: 1 file pushed, 0 skipped. 175.9 MB/s (65144 bytes in 0.000s)

shell@E5553:/data/local/tmp $ ./mtk-su -v                                      
param1: 0x3000, param2: 0x18040, type: 7
Building symbol table
kallsyms_addresses pa 0x40b98500
kallsyms_num_syms 77053, addr_count 77053
kallsyms_names pa 0x40c2ee00, size 941657
kallsyms_markers pa 0x40d14d00
kallsyms_token_table pa 0x40d15700
kallsyms_token_index pa 0x40d15b00
Patching credentials
Parsing current_is_single_threaded
ffffffc000318ee8+50: ADRP x0, 0xffffffc000fd8000
ffffffc000318ee8+54: ADD Rd, x0, 0x7d0
Possible list_head tasks at offset 0x278
comm swapper/0 at offset 0x4f8
Found own task_struct at node 4
cred VA: 0xffffffc063074300
init_task VA: 0xffffffc000fd87d0
Parsing avc_denied
ffffffc0002c63ac+20: ADRP x0, 0xffffffc001180000
ffffffc0002c63ac+24: LDR [x0, 0x964]
selinux_enforcing VA: 0xffffffc001180964
Setting selinux_enforcing
Switched selinux to permissive
starting /system/bin/sh
UID: 0  cap: 3fffffffff  selinux: permissive  
shell@E5553:/data/local/tmp # whoami
root
```

---

Install mtk-easy-su apk


Follow bootless root for Magisk 20+![^4]

---

Android Debug Bridge is not available on android 6.0 settings, following this to enable it[^5]

```
su
setprop service.adb.tcp.port 5555
stop adbd
start adbd
```

Next is to enable adb wireless on boot[^6] 

```
setprop persist.adb.tcp.port 5555
```

Removal

```
setprop persist.adb.tcp.port ""
```

---

[^1]: [Amazing Temp Root for MediaTek ARMv8 2020-08-24](https://forum.xda-developers.com/t/amazing-temp-root-for-mediatek-armv8-2020-08-24.3922213/)
[^2]: [Critical MediaTek rootkit affecting millions of Android devices has been out in the open for months](https://www.xda-developers.com/mediatek-su-rootkit-exploit/)
[^3]: [GSM Arena Sony Xperia C5 Ultra](https://www.gsmarena.com/sony_xperia_c5_ultra-7463.php)
[^4]: [Up-to-date bootless root for Magisk 20+!](https://forum.xda-developers.com/t/amazing-temp-root-for-mediatek-armv8-2020-08-24.3922213/post-82081703)
[^5]: [Enable wireless adb as root](https://stackoverflow.com/a/31327918/10025507)
[^6]: [Enable wireless adb on boot](https://stackoverflow.com/a/34219466/10025507)
