+++
title = "Networking My Parents' House"
description = ""
tags = [
    "networking", "unifi", "ubiquiti",
]
date = "2022-06-01"

+++

So before I began this project, it was clear that the network closet was a mess:

![Network closet is a huge mess.](/networking/one.jpg)

Wires and cables everywhere. The patch panel is unorganized. There's so much crap everywhere you can't even tell what's going on. I do want to say that most of this was not me. This was the previous owner. When we moved into the house the previous owner had already wired every inch of it with cat5e and coaxial. When installing Unifi AP's around the house I traced them down to here and connected them all to a switch. The reason you don't see a router or modem is because those are in a totally different room. For whatever reason the demark doesn't lead to the network closet. I'm sure there's a way I can trace it to the network closet, but then I'd have to invest in a multimeter, which I don't want to do just to trace coaxial. 

The house was originally wired in around the year 2000 and I am so thankful they actually wired it with cat5e. Would cost a fortune to have someone come in and rewire everything. Like there's no crawl space or attic that you can lead the wires through. It's all hard wired in. Half the crap on the wall is completely useless. That white mounted container thing is like some ancient security system.

There was even a 66 block in use at one point:

![66 block](/networking/two.jpg)

Just a bunch of early 2000s crap that no one had any use for anymore. At this point the house had 3 AP's and 1 AP in the pool house / AirBNB. The tiny 8 port switch was getting full. My parents had recently switch to YoutubeTV which requires large amounts of bandwidth to stream reliably. I knew the best thing to would be to have all the TV's hardwired instead of relying on Wifi. Wifi is honestly kind of annoying, especially with multiple AP's. You have to make sure all the AP's are on different channels and that their gain isn't too low or high. Also placement and direction are important too. It's really hard to optimize everything. 

Originally we were using ancient Unifi AP's from like 2012 that only used the 2.4 GHz frequency. As far as channels go we were at our limit. With 5 GHz you have 24 non-overlapping channels. And when we upgraded to the Unifi 6 AP's they made a huge difference, but the spots I had chosen to place the AP's wasn't the most optimal. If I could connect every single Ethernet port to a switch I could easily go through a trial and error and find the most optimal placement for the AP's. 