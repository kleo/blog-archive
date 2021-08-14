---
layout: post
title: "Disable PROLiNK H5004NK TR-069/CWMP"
category: routers
---

This was one of the routers from Globe a local ISP here in the Philippines when ADSL was still the standard. I still have a couple in use as access points.

It still requests **gbbthd.com.ph** every five seconds.

You can disable it with just using a regular browser.

Login/Setup	 (Defaults)[^1]

```
username: admin
password: 3UJUh2VemEfUtesEchEC2d2e
```

2. **Advanced** > **CWMP**

3. Right click the Enable box and inspect element, remove disabled

4. Right click the Apply Changes button and inspect element, remove disabled

5. Right click the Reset button and inspect element, remove disabled

6. Click Apply Changes

7. **Maintenance** > **Reboot** > **Commit Changes** > **Reboot**

---

[^1]: [Aztech DSL5001EN same admin password](https://gist.github.com/pongstr/8168585#file-globebroadband-md)
