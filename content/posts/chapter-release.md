---
title: "Chapters by TzYi - Out now!"
date: 2025-11-24T12:00:00+00:00
tags: ["code", "swiftui", "ios app"]
cover:
    # image: "/chapters/todo.jpg"
    # can also paste direct link from external site
    # ex. https://i.ibb.co/K0HVPBd/paper-mod-profilemode.png
    alt: "Chapters by Tzyi"
    caption: ""
    relative: false # To use relative path for cover image, used in hugo Page-bundles

---

Excited to announce a new app release to round out the year, Chapters!  It's a minimalist writing app with a few thoughtful design touches to help you write your next masterpiece. 

### Try It Out!

Download it now for free on the [ App Store](https://apps.apple.com/gb/app/chapters-by-tzyi/id6754342834).

### Cross Platform

It's also my first cross platform app, available on iOS, iPadOS, and MacOS.  Your data syncs seamlessly with iCloud (using SwiftData under the hood).  So if an idea hits you while you're out and about, you can quickly tap it out on your phone, then settle in with a coffee and iPad later to bring it to life. 

> Write on iPhone. Continue on iPad. Finish on Mac.

So how was using SwiftUI for cross platform? Few interesting issue cropped up during development.  The 'sheet' popups on the Mac had a fun bug where they where tiny, on iOS sheets get automatic sizing and look lovely but I found on the Mac you had to specify some size. 

SwiftUI textfields are suprisingly bad.  The actual editor part itself I thought was going to be a breeze, just use a simple SwiftUI 'TextField' component I thought...nope.   They are great for small text inputs but on larger fields they actually have a ton of issues so I had to revert to native UIKit implementations.  

### I love the iPad

I think my favourite version is the iPad.  I think the iPad is such cool device and wonderful form factor.  If you pair it with a nice bluetooth keyboard I think you;ll find Chapters is a perfect companion if you're into minimalist editors.  