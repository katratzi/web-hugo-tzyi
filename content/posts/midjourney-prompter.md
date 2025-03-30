+++
date = 2024-03-30T21:00:00+01:00
draft = false
tags = ["code", "web", "ai", "midjourney"]
title = "Midjourney Prompt tool with PetiteVue"
relative = false
+++

Ever tried keeping track of all your comma seperated tags when trying to craft the perfect Midjourney prompt? It's can get quite chaotic fast. That's why I built this [tiny prompt generator](https://midjourney-prompt.surge.sh) that helps you orgnaise and manage it a bit easier.

### What's the Deal?

This little web app helps you build Midjourney prompts by breaking them down into bite-sized pieces. Think of it as a prompt sandwich maker - you just pick your ingredients (subject, style, lighting, etc.), and it assembles everything into a tasty prompt that Midjourney will love.  You can import/export the file as json if you want to use it again another time. 

### The Tech Stack

I built this using [PetiteVue](https://github.com/vuejs/petite-vue), which is like Vue.js but on a diet - super lightweight and perfect for small projects. It's amazing how much functionality you can pack into just a few kilobytes! Here's what makes it tick:

- **PetiteVue**: For all the reactive magic (and it's seriously tiny - like 6kb tiny!)
- **Skeleton CSS**: It's a pretty old micro css framework, but it's tiny and awesome.  
- **Surge.sh**: For hosting (because who needs a complicated deployment setup?)

The whole thing is just a single HTML file with some JavaScript sprinkled in. No build process, no bundling, just pure simplicity. There's a great appeal to just simplifying development down to such a simple little process. 

### Try It Out!

Head over to [midjourney-prompt.surge.sh](https://midjourney-prompt.surge.sh) and give it a whirl. 
