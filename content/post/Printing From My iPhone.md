+++
title = "Printing From My iPhone"
description = ""
tags = [
    "printers", "dell", "ios",
]
date = "2022-06-27"

+++

For the longest time I've never been able to print from my iPhone to the Dell printer in my parent's house. I'm not exactly sure when we got the printer but I know it's at least been like 7+ years. The printer in question is the [Dell 2155cn Color MFP](https://www.dell.com/support/home/en-us/product-support/product/dell-2155cn-cdn/overview). According to the copyright on the [user guide](https://dl.dell.com/manuals/all-products/esuprt_printers_main/esuprt_printers/dell-2155cn-cdn_user's%20guide_en-us.pdf?dgc=SM&cid=626927&lid=spr7164772008&refid=sm_APPLE_BUSINESS_CHAT_spr7164772008&linkId=170749771), the printer was released in 2010. That makes the printer a decade+ old.

When I first tried printing from my iPhone to this Dell printer some 5 years ago, iOS was unable to find the printer on the network. At the time, I assumed it was because the printer was so old, and that it was probably using some ancient protocol that only worked on Windows. Back then I'd just give up and print from my computer instead. Why waste time figuring out how to print from my phone when it takes like 20 seconds to just walk over to my desktop and print from there instead? Fast forward to now and I've deemed that unacceptable. I was going to get to the bottom of this and figure out why the hell iOS couldn't find my printer.

When I first attempted to print from my phone I used an app called Printer. Which Printer app? It doesn't matter. After installing multiple of these generic printing apps, the method they all use to add a printer is with something called [AirPrint](https://support.apple.com/en-us/HT201311). When searching through the printer's user manual I could find no mention of AirPrint. So I can only assume that this printer is not AirPrint compatible. (AirPrint was released in late 2010, so it was technically possible.)

After deleting all the useless printing apps I went back on the app store and searched for the Dell Printer app. Only, when I submitted my search, I was met with just the same old generic printing apps. No Dell printing app to be seen. That seemed a little odd to me. What kind of business is going to produce printers but not make an app to encourage us to buy their overpriced toner? I decided to do a couple google searches and finally figured out the answer: [Dell discontinued producing printers](https://www.theregister.com/2016/09/19/dell_quit_printer_business/) and thus decided not only to stop updating their [printing app](https://www.dell.com/support/kbdoc/en-us/000135610/how-to-install-and-configure-the-mobile-print-app-for-dell-on-ios-devices), but to wipe it completely off the App Store. Now, if you go to [Dell's website](https://www.dell.com/en-us/work/shop/printers-ink-toner/ac/4014) you'll still see printers listed for sale, but you'll quickly notice that none of them are Dell brand. Of course Dell isn't stupid enough to discontinue selling toner. I am curious how long they'll be selling their toner for. I imagine eventually most home offices/businesses are going to upgrade and replace their lowly Dell printers. I give it around 10 to 15 years.

At this point I feel like most people would've just given up and moved on to accepting that they'd never be able to print from their iPhone to and an old Dell printer. But I wasn't going to give up that quickly. After realizing that there was no Dell printing app I started wondering if there was some kind of app that would allow me to manually enter in the printer's networking info. When adding the printer to a Chromebook that was exactly what I had to do to get the device to connect to my printer. I started once again downloading more random generic printing apps. One by one I deleted them as they searched using AirPrint. I was extremely close to giving up until I finally found the one. I finally found the holy grail of printing apps. Introducing: [ePrint Free](https://apps.apple.com/us/app/eprint-free/id304220730)

At quick glance this looks like the last app you'd want to install for printing. It has that unpolished/blocky look from pre-iOS 7. Surprisingly, the app was last updated in 2014 for support for iOS 8. And now here it is chugging along working fine with iOS 15. What makes this app so great? It actually finds my printer and allows me to print with it. I can finally print directly from my iPhone to this dumb Dell printer. 

![ePrint Free actually letting me print!](/printer/2.png)

Now the question is why does this old app discover my printer on the network, but all current apps can't?

After doing a little bit of research I think I figured it out. I want to say I am no expert on printer protocols so my hypothesis might be a little off. One of the first things I noticed when using this app was that when adding a printer it was using something called Bonjour. The picture below shows it to the left of the search printers text. So what is Bonjour? [Bonjour](https://developer.apple.com/bonjour/) is just another title for something called zero-configuration networking (zeroconf). I'm not going to go into [detail](http://zeroconf.org/) about what zeroconf is, but the gist of it is that it allows devices to easily create their own network automatically, not requiring any complex set up from a human. Part of getting devices to network themselves is by making it very easy for each device to discover one another. This is exactly what Bonjour does. It allows devices to be easily discoverable on a network. This is perfect for printers. Businesses don't want to have to deal with customers who are having trouble getting their printer to work and end up returning it. You want to make printers as easy as possible to set up, and part of that is by making the discovery and connection to the network automatic. 

![ePrint Free uses Bonjour](/printer/1.png)

So does this app only work because it uses Bonjour and the other apps use AirPrint? No, because AirPrint uses Bonjour. Bonjour is built into AirPrint. [Here](https://apple.stackexchange.com/questions/402633/what-is-the-difference-between-airprint-bonjour-and-rendezvous) is a great explaintion on Stack Exchange. AirPrint is the actual protocol that does the printing, while Bonjour simply allows for the discovery of the printer. What I believe is going on here is that AirPrint could easily find my printer. AirPrint won't show it because it's not AirPrint compatible, even though it could show me it and just allow me to print with a different protocol. 

In summary, ePrint Free finds my printer with Bonjour and then uses a [protocol](https://en.wikipedia.org/wiki/List_of_printing_protocols) like LPD, IPP, or AppSocket to actually print the document. Hopefully Apple doesn't remove this app for being so outdated. Not that I really print often with from my iPhone. Sometimes I just want to print a picture directly from my phone and not have to email it to myself to print it off from my desktop. (I don't like the idea of automatically uploading all my images to the cloud.)

Long live ePrint!