---
layout: post
title: My computer is the hell I imagined, and it's fine
---

I remember a couple of years ago thinking about flatpak and systemd as the two "harbingers of the end of Linux as we know it".

I was probably right, although not in the way I expected.

## The dystopia

The old me thought that eventually systemd would swallow the whole operating system with all of its components, and that every program we used to run natively would get weighed down by a useless runtime just to be called an "app".

Also that so called "immutable" Linux distros would eventually cage us like other operating systems are trying to do (namely Android and iOS).

Can you imagine? A world where we don't have the freedom to use the packaging format that we prefer or an init system that's just less bloated!

Horrible, right? It means losing the freedom that Linux has always granted us.

Heck, might as well be stuck with the GNU coreutils and clib!

## Is it so bad though?

Why not try and formulate this differently?

I now still believe that, yes, we might not get back to running most of our programs outside of containers and sandboxes.
This is actually really nice though, since we don't need to worry about different packaging formats, and can just focus about "the linux ecosystem" instead of trying to actually care about all the small differences of every distro. Yes, this also means letting distro maintainers only handle core packages, focusing a whole lot more on security instead of packaging everything one might ever need in their home and professional use of a computer. Security is also becoming less of a problem when we can now easily isolate applications (focus goes on "easily", I'm talking to you SELinux and AppArmor).

Even systemd, not only can it simplify our container stack thanks to systemd-nspawn, but only having a single init system allows maintainers to, again, focus on more important stuff (such as actually providing proper services/units since a good amount of software still only ships a daemon that needs to be started manually).

Immutable distros are the thing that makes all of this come together.
Having a system that guarantees correct operation comes at the not-so-low price of not being able to modify it.
But why would we need to modify our system when we can just use a container? In a container I can do just about anything I'd need without too much overhead.

Slowly but surely, it's all coming together to actually bring a safer and trouble-free desktop experience for everyone for the first time in the Linux world!

Soon VanillaOS, Fedora Atomic (perhaps also UBlue?) and OpenSUSE MicroOS will be what we'll suggest to newbies, allowing them to have a functioning system that won't break on them for reason they won't understand yet.
