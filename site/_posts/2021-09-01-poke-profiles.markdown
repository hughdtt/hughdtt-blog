---
layout: post
title:  "A little passion project: Poke-Profiles"
date:   2021-09-22 12:38:25 +1000
categories: programming project
featuredPost: true
excerpt: Hey all, I've been working on a little web app for the past month and half. I wanted to write a brief summary of the inspiration, process, what the current product looks like and perhaps a bit of reflection.
---
## Introduction
Hey everyone, 
Happy to update that I've just wrapped up the first release of a little project that I've been working on called Poke-Profiles! It's been a bit of a challenge to get together some time after work/ weekends to spend time on this. However, I've finally managed to get it to a point where I'm fairly happy with it. I wouldn't call it perfect but I had a pretty good crack at it. I'm actually quite proud of the result. It's possibly the best thing I've been able to produce all on my own. You'll be able to have a look at it [here](https://github.com/hughdtt/poke-profiles). 

## Inspiration

I'm trying to remember exactly what kickstarted the sudden surge of motivation to start a project *and then* try to get it completed. Anyway, somehow while browsing the internet I stumbled upon [this](https://dribbble.com/shots/2859891--025-Pikachu/attachments/2859891?mode=media). My first immediate thought was 'this is so epic'. The second thought was 'wait at minute, I remember coming across a PokeAPI library a while ago. Shouldn't I be able to make this?'. And so, off I went.

## Planning

I have a tendency to procrastinate on youtube. *Don't judge me, I'm sure everyone does.* Regardless, I stumbled across this guy - [Florin Pop](https://www.florin-pop.com/). He did a fantastic challenge called "10 coding projects in 10 hours". I felt super inspired by this and a lot of the javascript groundwork stems from these projects. You can check out the github [here](https://github.com/florinpop17/10-projects-10-hours). 

Anyway, enough fanboying. I basically used these projects to set out a scope, technology stack and architecture. I didn't really want/ need to build a full on fullstack application (like the ones I do for work). Reason being that it would take a lot of work and there's only one me with not a lot of time. When in doubt, I can always rely on the basics. Simple HTML/CSS/Javascript will do the job. Since it's my project, I can make it as simple or as complicated as I want. That's a freedom I can afford. Of course there are drawbacks and advantages to just using vanilla javascript but I'll take it as a learning exprience.

The main star of the project really though is [PokeAPI](https://github.com/PokeAPI/pokeapi/). All I really need to do is connect this to my page and when I do a search for a pokemon, it'll bring me all the information I can possible want about that searched pokemon. It's like magic. 

The main challenge is then implementing the layout and make it look impressive. It needs to work across mobile and desktop platforms - in this project I worked with a mobile-first design strategy. You can read more about it [here](https://css-tricks.com/how-to-develop-and-test-a-mobile-first-design-in-2021/).

The second challenge is optimization, I want the experience to feel seamless and fast. Luckily for me, the guys at PokeAPI also made a little javascript wrapper that uses serviceworkers to sort out caching for images. Basically that means once you load an image, it hangs around so that if you search the same pokemon again it'll load faster.

With those things nutted out, I was ready to get cracking.

## Features

#### Search function

There's a jQuery UI widget integrated into the app to sort out the search functionality. Basically works as you would expect. Type in any letter and it'll filter search for a list of relevant pokemon in alphabetical order. It'll also highlight the letters you search for aswell, neat!

You can search by either clicking a select option or typing out the name entirely and pressing enter.

Currently, there's no hard validation warning when you type in a pokemon that doesn't exist. There's a little unintended feature from the search filter that tells you it didn't find any pokemon with your search parameters though. Kinda serves the same purpose, but doesn't let you know a search as failed on submission. (*I'll add this later, I swear*)

<details>
<summary>Images</summary>
<h5>Search functionality</h5>
<img src="/assets/poke-profiles/search.PNG" alt="search" />
</details>

#### Pokemon details

When you do a search, you should get the following details:
- Pokemon ID
- Pokemon Name
- Pokemon Japanese Name
- Height
- Weight
- Region
- Type (as image)
- Stats (HP/ Attack/ Defense/ Sp Attack/ Sp Defense/ Speed)
- A randomly chosen pokemon description (some of you may recognize it's the official pokedex entry description from the anime)
- The background color will also change depending on the pokemon's primary type

The information layout is slightly different for mobile version because it looked better that way. 

#### Loading icon

When you do a search and the app is taking it's sweet time to bring you all the information, you should see a loading icon until it's ready to show you the pokemon.

<details>
<summary>Images</summary>

<h5>Loading animation</h5>
<img src="/assets/poke-profiles/loading.PNG" alt="loading" />
</details>

## Challenges
I don't really want to make you sit here and read through all the challenges I went through so I'll just riff off that main ones and how I overcame them.

#### Problem 1 - Sticking to the design layout
As you can tell, the layout for the desktop version is not really in a standard web template. I had to experiment quite a bit to get it really nice the way it is. Of course, you can also tell it doesn't match the design template 100%. Reason for this was because the image size gets really pixelated when I scale it up. Since I'm grabbing the image from an API and don't really want to do anything more than scaling it up. I can just re-arrange things to make it look nice. In this case, I should treat the design template as a guide rather than strict ruleset. Plus, it was a really good experience to train my eye for these type of things. I used CSS Grid to implement the design and let me tell you, the **MVP Tool** was the firefox developer console. It makes generates grid guidelines which make it really easy to see whether things align and helps me positions things easier. (Also helped me get my head around CSS Grid as I had never really used it before - TLDR; you should basically treat it like excel cells)

#### Problem 2 - Loading times
In an effort to make my code look cleaner, I re-wrote some things and wrapped the API calls in async/ await functions. I also figured out that I could get the Japanese translations from the API call as well - but this needed me to make two API calls instead of one. This actually slowed down my code a little bit since the second call would have to wait for the first call to finish before executing. I haven't been able to find a good solution that I could easily implement. The next best thing was to add a loader animation so that at least the user would know to wait rather than just looking at a frozen screen until something changed.  

## Looking backwards
I know the application isn't perfect. There's little bits here and there that could use some work. I've tried my hardest to crack down on the majority of bugs and feature enhancements to get it to its current state. I think if I don't do a bit of reflection now to remind myself what the original goal of the project was, I might get caught up on a perpetual loop of enhancing these minor things to make it perfect. 

While that's nice to do, I don't think there's much progress to be had in spending an extra chunk of time sorting them out. I'm a big believer in the 80/20 rule and I think it applies here pretty well.

I started just wanting to build *someting*. I wrung out a scope and mostly stuck to it. I built a fairly awesome looking site and wrote documentation for it. I learnt so much along the way; got to understand what I'm comfortable doing and what my shortcomings are. It's not about the destination but the journey. Plus I've used up the initial spark of motivation weeks ago. My discipline has gotten me this far and I only have a little bit of strength left to write down my thoughts and plans for the future if I ever decide to revist the project.

## Looking forwards
Now that I'm writing this reflection piece, I'm actually feeling quite fulfilled with the amount of work I've been able to get done. I'm also a little excited to wait a while and get back to work on it. Which is good I think! 

Like I said, I've tried to keep documentation up to date on the github repository. There's a list of changelogs there. But basically the major things to work on are the loading times and perhaps a refactor. It could also do with some fancy animations and sounds effects. Oh! And I should probably get the cool pagination things done. I'm imagining a little scrolling effect I could add. There's actually a bit to do!

For another time though. 😀

## Wrapping up
That's all folks! Thanks for reading until the end. If you're interested in what else I have to say, you can check out my other posts below. 

Hugh

