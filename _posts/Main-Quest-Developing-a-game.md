---
layout: post
title:  "Main Quest, Developing a game"
date:   2023-10-23 19:11:17 +0200
categories: game development
comments: true
---

Have you ever started a development project only to abandon it midway?  
Not yet?  
Then let's embark on an adventure together!

# Introduction:
Too often I have thought of making a game, or game engine, started a project, worked on it for a few weeks until maybe months and then left it
as I ran into either difficult issues, eternal rework cycles or just lost interest because of my day job taking away all my motivation to also program in the evening or weekend, plus of course my wife also now and then requires my attention.

I never mind it, I learned a lot during all those projects and that's really where the fun is for me. During 
my projects I have tried many game engines like Unity, Unreal, Godot, and Bevy, though I liked the quick results you could achieve with those 
engines I was always left with a feeling that I needed to know how it was implemented behind all the layers of abstraction, and though Godot, and Bevy are
excellent open source engines that I very much enjoyed exploring and building from source I always kept having the feeling that it contained way to much features for what I required. I can't exactly recall how often I have started writing a game engine on my own, though my personal github account mentions I have currently 73 repositories of which I believe at least 50% are game engine projects. I have tried creating engines in c, c++, c# and rust, often getting quite far, some even containing an functional editor to some degree but in the end they always get abandoned for some reason or another.

## Is this time going to be different?
**No**, I will start the project, enjoy working and learning from it, create another set of repos containing thousands lines of code but in the end 
I will most likely abandon it. 

But there is something going to be different, this time I will document my failure for everyone to see, in the hope of being of help to
any other person dipping his toe in the wide and interesting world of game development. 

As a challenge and to keep it interesting for me we are going on an adventure into the world of a new programming language called Zig.

![The logo of zig](/assets/img/zig_logo.png){: width="300" height="105" }

## Why Zig?
Zig is a new programming language still in early development. As mentioned I worked on quite a bit of side projects
in all kinds of languages and during all those projects I got an appreciation of the simplicity of plain c. I love the control it gives me
and prevented me spending way too much time on coming up with way too complex abstraction levels using all kinds of c++ template magic that whenever I made
an error can cost half a day of figuring out. Same with rust, I found the security it offers great but I often had the feeling it became to abstract to my liking.

But of course C is not without its issues, it's a language more than 50 years old and though there are newer versions they never changed the
language in any real significant way since c99. This age can be both good and bad, good because you can find almost all your questions answered somewhere on the internet. 
It's a real simple, and very much proven language, but in this day and age some newer concepts have appeared that can be very nice to have that is not supported by c, or is somewhat supported but than we would need to use the awful preprocessing C macros. One of the biggest for me would be generics. Being able to write reusable code for different types can really help in the development speed, and though you can somewhat achieve the same with c by using void pointers or macro's it never really felt as a decent solution. 

This is where Zig comes in, You can see it as C (very simple, and close to the hardware) but it also contains some nowadays standard things like namespaces and introduces some very interesting new concepts like compile time programming using the language itself, no macros or templates and a build system using the language itself. In some cases, it can be even closer to the hardware than C as it supports even arbitrary bit width integers like u1 or u7. Another notable feature is being able to write tests directly next to your code, no external libraries necessary.

Talking about external libraries, this time I'm going to challenge myself to try to create my game without external libraries other than the zig std.

Learn more about Zig's features [here!](https://ziglang.org/learn/overview/)

## You said no external libraries!?
Yes you heard it correctly, for me this is not about the destination, we know what that is most likely, (looking at you my 73 git repos containing stale projects.)
It's about the journey, and by excluding external libraries I can hopefully extend this journey in the hope of keeping my interest, letting me share as much as my findings with you as possible.

![A programmer with a quest](/assets/img/running_programmer.jpg){: width="256" height="256" }
## Quests

Our journey will be dangerous and filled with peril, for as far as I can see. We will have countless quests to overcome and, some of the most daunting quests 
include:

- **Writing an OpenGL renderer**  
  I know, I know, it's not Vulkan, but still render engines are a challenge and I would like to make at least some progress.
- **Writing asset management system**  
  Sigh, goodby stb_image.h
- **Translations system**  
  This one gets forgotten all to often, usually better to do this right from the start.
- **Mathematics**  
  Unfortunately no GLM for us, but Zig has something else up it's sleeve.
- **Windowing and Input handling**  
  Ouch, no GLFW, Hello win32 API!

And countless others, also we might find many side quests on the road that have us investigating 

- **CI/CD**  
  Curious to see how many commit's containing "fix" as message I this time need.
- **Font rendering techniques**  
  Help!

And many others.

## In Conclusion
With this journey in mind I hope to keep you entertained and help you learn something.
If you have any questions or suggestions, just let me know in a comment and who knows we can become friends along the way.