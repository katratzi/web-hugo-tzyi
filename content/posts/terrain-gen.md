+++
date = 2099-10-21T15:47:28+01:00
draft = true
tags = ["code", "unity",]
title = "Unity - 2d Terrain Generation"
[cover]
alt = "terrain generation"
caption = ""
image = "/uploads/poster-terrain-gen.jpg"
relative = false
+++

At the outset we knew we wanted to lean heavily into procedural generation, much like civ, to make the game infinitely replayable.  One of the early tasks for the game was to generate maps.  There are a number of approaches available but I found a great algorithm for [cave generation with cellular automata](https://gamedevelopment.tutsplus.com/tutorials/generate-random-cave-levels-using-cellular-automata--gamedev-9664) that seemed like a great fit. 

## How the Algorith Works

It's a fairly simple algorithm and produces some pretty nice landmasses.  In cellular automata a cell can either be on or off, often refered to as *alive* or *dead*.  When counting neighbours it refers to all the cells that surround that particular one, and in this case we count those that are alive. 

![](/uploads/cellular-chance-to-start-alive.gif#center)

- Create a grid of cells of the desired size
- For each cell in the grid, it has a '%' chance to start *alive*.
- Then run the following simulation step to smooth out the result and generate the land masses.
- For each cell in the grid we're going to count the number of alive 'neighbours' at each step...
    - If *alive* and *neighbours* < *death limit*, this cell will become *dead* on the next simulation
    - If *dead* and *neighbours* > *birth limit*, this cell will become *alive* on the next simulation

By adjust these few parameters above, it was possible to create a number of useful presets for different types of terrain.  We store these values with scriptable objects so we can reuse and modify the values more easily. 

![](/uploads/cellular-tweaking-values.gif#center)

## MonoBehaviour OnValidate()

When playing around with the values, like in the above gifs,  it's incredibly useful to use sliders and also be able to see the results immediately without having to either restart or setup some manual refresh.  This is conveniently quite easy in Unity Monobehaviours.  Sliders just need an attribute to work. 

    [Range(0, 100)]
    public int chanceToStartAlive;

And when ever you change a value from the editor, you can use an in build method in MonoBehaviours called OnValidate to run another piece of code.  
   
    private void OnValidate()
    {
         RegenerateMap();   
    }

