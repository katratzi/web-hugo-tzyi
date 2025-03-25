+++
date = 2022-10-21T15:47:28+01:00
draft = true
tags = ["code", "unity",]
title = "Unity - 2d Terrain Generation"
[cover]
alt = "terrain generation"
caption = ""
image = "/uploads/poster-terrain-gen.jpg"
relative = false
+++

At the beginning of the project there were effectively two main choices for map design.  The first would be to make bespoke maps, aimimg for historical accuracy and adopting real Scottish/British geography.  A game like Total War takes this approach and does an excellent job with it.  In our case though we to be inspired by Scottish history but not beholden to it for a feel that is 'just left of reality'.  So instead we wanted lean heavily into procedural generation.  This would allow us to create effectively millions of different maps for maximum replayability.  Civilisation is a prime example of the benefits of this.  It also has the added benefit of keeping the asset creation needs minimal which when you're a wee developer like us is super helpful. 

>..."millions of different maps for maximum replayability."

So how do you go about generating maps?  If you search in google there are a number of approaches available, commonly based on [noise functions](https://www.redblobgames.com/maps/terrain-from-noise/).  But as we are using a square grid system I found a slightly different technique, [cave generation with cellular automata](https://gamedevelopment.tutsplus.com/tutorials/generate-random-cave-levels-using-cellular-automata--gamedev-9664), that seemed like a great fit. 

## How the Algorithm Works

It's a fairly simple algorithm and produces some pretty nice landmasses.  In cellular automata a cell can either be on or off, often refered to as *alive* or *dead*.  When counting neighbours it refers to all the cells that surround that particular one, and in this case we count those that are alive. 

![](/uploads/cellular-chance-to-start-alive.gif#center)

- Create a grid of cells of the desired size
- For each cell in the grid, it has a '%' chance to start *alive*.
- Then run the following simulation step to smooth out the result and generate the land masses.
- For each cell in the grid we're going to count the number of alive 'neighbours' at each step...
    - If *alive* and *neighbours* < *death limit*, this cell will become *dead* on the next simulation
    - If *dead* and *neighbours* > *birth limit*, this cell will become *alive* on the next simulation

Each time you run the simulation step it starts to form the land masses themselves and eliminate some of the rougher edges resulting a massive set of nice maps to play on.

![](/uploads/cellular-tweaking-values.gif#center)

## Unity Editor Tools

When you want to play around with these values, like we do in the above gifs,  it's incredibly useful to use sliders and also be able to see the results immediately without having to either restart or setup some manual refresh.  This is conveniently quite easy todo in Unity. To set up the nice range sliders you just need a wee header attribute like so. 

    [Range(0, 100)]
    public int chanceToStartAlive;

To make it interactive, you can use an in build method in MonoBehaviours called *OnValidate* to run code whenever an attribute is changed in the editor, like the smooth count or death rate above.  This is as simple as... 
   
    private void OnValidate()
    {
         RegenerateMap();   
    }

With this simple setup, we where able to start experimenting with the values until we got fairly consistent results for different type of maps.  In our case we've found a few awesome presets that we are experimenting with.  We have smaller mosftly filled maps that allow for more action packed games.  Nice medium sized maps that offer a great balance between the gameplay styles.  And larger maps that require more exploration and risky ocean crossings for players that enjoy a challenge.

We look foward to welcoming you to explore the lands of Mantle Nan Ceiltach soon.  Please bookmark and follow us on social media to stay updated for more behind the scenes logs.

