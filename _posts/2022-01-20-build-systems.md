---
layout: post
title: Build systems are evil
author: Max
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

Oh and of course this problem is not limited to Java. For anybody that's interested, this is how things are going with Python
> https://drewdevault.com/2021/11/16/Python-stop-screwing-distros-over.html

![xkcd.com/1987](https://imgs.xkcd.com/comics/python_environment.png)

And don't get me started about the mess that is JavaScript with their thousand CLI tools introduced by the next revolutionary library/framework.

Luckily Rust is safe enough, right? Imagine if someone thought that it was a good idea to create
entirely separated tools along with a new type of project setup.

Except that it's exactly what happened with [Tauri](https://tauri.app/)!

I'm only want a half-decent, standardized, simple way to build software.
Am I asking too much?

Guess I'll stick to good old makefiles for now.
