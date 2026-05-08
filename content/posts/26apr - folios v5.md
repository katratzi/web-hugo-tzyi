---
title: "Folios - cover up"
date: 2026-04-22T16:25:42+01:00
draft: true
tags: ["folios", "ios app", "swiftui", "release notes"]
---

There was a focus on performance for this v5 release as well as some nice little quality of life features.  The slideshow is now smart and only gets the full res image for the current and prev/next, so it's much quicker to load that view as well being more memory efficient.  There's a new little settings menu that allows you to set the masonry image size (small, medium, large) and the a button for setting cover images which helps scrolling on larger collections.  

On the cover image, this was interesting bit of SwiftUI.  If no cover iamge is set, I sort and pick the first one from the list.  Seems straightforward enough right, but in order to sort it has get that blob data first not just the 'sort' property, so it can be quite slow.  This little piece of code below is all it was. 

{{< figure align=center src="/folios/releases/v5 code original.jpg" title="Original cover code" >}}

Here's an interesting glitch I found in SwiftUI.  Setting the cover image explicitly means I don't have to sort at all and it's way faster.  So clever me I put this little change in, where if we don't have one set just set it as the first.  

{{< figure align=center src="/folios/releases/v5 code sequel.jpg" title="Code that had a sneaky bug" >}}

Here's the catch though, I discovered if the iCloud data is syncing, so you're getting say 100 images for a new album, this code can trigger early and break the sync.  It was quite a sneaky bug.  So thankfully I caught it before release and now there is simply a little button in the settings menu that sets any albums that don't have a cover image to the first.  It's not needed, but if you have a large collection it really improves scrolling the main albums views. Enjoy!

[ Folios by TzYi on the App Store](https://apps.apple.com/us/app/folios-by-tzyi/id6758107784).


  



