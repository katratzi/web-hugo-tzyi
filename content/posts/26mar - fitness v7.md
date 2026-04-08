---
title: "Fitness - bug fix"
date: 2026-03-21T16:25:42+01:00
draft: false
tags: ["fitness", "ios app", "release notes"]
---

There's been a hard to track down bug relating to loading the data in the app that I think I've finally squashed.  Your exercises and workouts and stored as json files in an icloud drive.  This keeps them safe, backed up and syncable when you move phones.  However sometimes (particularly after a phone update) the file isn't ready to read when the app loads.  So the app start, tries to get file from icloud which triggers downloading it, but doesn't always get it and it looks like you've lost your exercises.  

**If your exercises are missing, close the app and restart**

With some help from Claude, I think this is fixed or at the very least should show up less often.  A future proof bit of work for this is to move over to SwiftData, which didn't exists when I oringally developed it, but it's a pretty major refactor and tricky to handle the migration.  But it is on my mind.  

Anyway hope you enjoy using the app and find it even more reliable and helpful for your fitness journey.

[ Fitness by TzYi on the App Store](https://apps.apple.com/us/app/fitness-by-tzyi/id6473851299).


  



