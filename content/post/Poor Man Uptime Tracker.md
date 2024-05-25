+++
title = "Poor Man's Monitoring Tool"
description = ""
tags = [
    "uptime", "monitoring", "cmd", "powershell"
]
date = "2024-05-04"

+++

A couple days ago I was messing around with the football-data.org API when suddenly my internet went out. With it being 1am, it was a clear sign for me to go to bed, but I ignored it and just hopped on my phone for a bit. 30 minutes later I noticed the internet was still out and I was kinda pissed. (As if I was doing anything actually important.) Usually these outages only last about 10-15 minutes or so. I then decided to think more rationally and realized it was probably some maintenance upgrade since the outage started almost exactly at 1am. I was curious how long this outage would last and decided to create the greatest uptime script known to mankind:

```
@echo off

:internet
ping 8.8.8.8 -n 1 | find "Reply" >> gimmeINTERNET!.txt
echo %time% >> gimmeINTERNET!.txt
goto internet
```

Forget Uptime Kemu, this batch script is clearly better and much more sophisticated. 

The next morning I woke up to this master piece:

![Finally getting replies back at 7:35am](/static/poor_man_uptime/uptime.png)

Through my genius and ingenuity I was able to figure out that the network went back online at 7:35am. Doing some quick math the maintenance took over 7 hours. All that maintenance and my internet speed still did not improve, pathetic. 