---
layout: post
title: Build systems are evil
---

Who the fuck thought that having a shitload of
complex build systems was a good idea?

Alright, so.
Make or a shell script isn't enough and people got tired of using Perl.
Let's rule out the three sanest options.

Most of the new shiny programming languages have their own solution
for building software, Rust has Cargo, Kotlin has scripting, Zig is pretty much a build system itself
and even Go has something to build its software without too much of a hassle (perhaps except with cgo)

Then why the fuck does Java, a language that is still heavily used and maintained
by corporations today, still need to have a shitton of absurdly complex build systems?

Seriously, it's ridiculous, a language that's stupidly easy (albeit ugly), that every moron
in computer science will need to touch at least once, needs to be made complex by degenerate third party tools.

Oh and of course this problem is not limited to Java. For anybody that's interested, [this is how things are going with Python](https://drewdevault.com/2021/11/16/Python-stop-screwing-distros-over.html).

![xkcd.com/1987](https://imgs.xkcd.com/comics/python_environment.png)
> [xkcd.com/1987](https://xkcd.com/1987/)

And don't get me started about the mess that is JavaScript with their thousand CLI tools introduced by the next revolutionary library/framework.

Luckily Rust is safe enough, right? Imagine if someone thought that it was a good idea to create
entirely separated tools along with a new type of project setup.

Except that it's exactly what happened with [Tauri](https://tauri.app/)!

I only want a half-decent, standardized, simple way to build software.
Am I asking too much?

And I would be more than happy to use makefiles or whatever the language tells me to use, but with how things are going
I need to completely change my project format just to make a UI. This is absurd.

Of course even the C/C++ world has been infected. Not only we have another shitload of build systems, but what is currently the industry standard
is an utter mess!

I often disagree with the Suckless philosophy, but they do share my "love" for build systems, so
I'll allow myself to [quote them](https://suckless.org/sucks/) this time.

> cmake (written in C++) - so huge and bloated, compilation takes longer than compiling GCC (!). It's not even possible to create freestanding Makefiles, since the generated Makefiles call back into the cmake binary itself. Usage of cmake requires learning a new custom scripting language with very limited expressiveness. Its major selling point is the existence of a clicky-click GUI for windows users.

Are we really going to simply not care that one of the core parts of a programming language, the compilation phase, is getting absurdely complex with no real benefit?

Because let's face it, there is no added benefit to all of this madness.
Following a _simple, yet extendable, unified_ standard for a programming language (e.g. only using cargo in Rust) could just make everyone happy.
But no, because enough is never enough.

Can't we just accept that something is simple, yet complete without declaring it dead?

Perhaps this is the single rule that has always been true in the software development world. Enough is never enough.

```
 _______________________ 
< Gradle ain't grooving >
 ----------------------- 
        \   ^__^
         \  (xx)\_______
            (__)\       )\/\
             U  ||----w |
                ||     ||

```
