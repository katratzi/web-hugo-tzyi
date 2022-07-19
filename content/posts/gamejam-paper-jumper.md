+++
date = 2022-07-03T09:00:00Z
title = "GameJam - Paper Jumper"
tags = ["gamejam", "godot", "code", "godot-vs-unity"]
[cover]
alt = "cover image for paper jumper game"
image = "/uploads/paper-jumper-cover.jpg"
relative = false
+++
Something a little different, I made a wee platformer game!  So we are developing in Unity, but recently I was curious to see what Godot was like for development and I thought best way to test it out was to make a small game. 

Presenting - [Paper Jumper!](https://tzyi.itch.io/paper-jumper) - Play now on itch.io!

It's a very simple wee platformer and was fun to put together, please have a go and leave your thoughts over at itch.io.

[![Paper Jumper Gif](/uploads/paper-jumper-clip.gif#center)](https://tzyi.itch.io/paper-jumper)


## Godot early thoughts

*It's tiny and great!* - Coming from Unity, which is a pretty massive install and now needs it's own launcher to handle all the different versions, Godot was a breath of fresh air.  It's download size is <100Mb and the install size isn't much bigger.

The in built scripting language and editor, GDScript, I also quite liked.  The syntax was easy enough to pick up.  The lack of brackets and semi-colons, once I got used to it, is now something I wish C# had as I like the brevity.  Having the code editor built-in is *rad* and it's pretty good too with autocomplete.  I did miss coding in VSCode and it's more powerful editing, and apparently you can get that setup so I might try that for the next gamejam.

For 2D pixel art games it's clearly a great fit.  For Unity you'd want to install a couple of packages for a 2d platformer (in particular I'm thinking of the tile system and I think there's a pixel perfect camera too).    Godot has all of these ready to go, and the 2D nodes and tools feel more native to 2D, i.e. the units are pixel based ... It's all very nice.  

Couple of concepts I struggled with...there is scene graph in godot but I couldn't easily disable/enable a node like you can a GameObject in Unity.  Instead I had to remove it from the scene, save it in a variable, and reinstate it when needed...not sure if I'm missing a better approach there.

When I was setting up the one-way platforms I was duplicating the node (a StaticBody with a CollisionShape child) but I always had to set the rectangle collider with 'make unique' otherwise changing one would alter the others?  I'm not sure what's going on there at all.  Using different scenes in Godot, which work like prefabs in Unity, the shared properties made sense, this did not.

![](/uploads/paper-jumper-screenshot.jpg#center)

## Waiting for Godot 4.0

There's a big new  version in alpha and  looks to have tons of improvements, I noticed the tile system has been reworked and updates to the 3d renderer, but will be a breaking change from 3.   I wouldn't abandon Unity for our current project, largely as I'm so proficient and familiar with it and C#.  Once the new version comes out though I'll definitely give it a look and as time permits I'll continue learning about the engine on the side.




