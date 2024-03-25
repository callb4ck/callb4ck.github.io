---
layout: post
title: Bs-free Linux distro guide v1
---

I made this article to help people pick a Desktop Linux distro that works for them without any marketing bullshit attached to it.

Honestly I'm astonished by the sheer quantity of similar articles that seem automatically generated with the same contents and absolutely full of bullshit marketing slogans such as "distro for developers/gamers" or even showing the same forked system with a customised look and feel as its sole purpose.

---

# Glossary

I'm assuming the reader knows the meaning of words such as "distro", "package" or "repository", however I'll be using some other non obvious technical terms, let's see what they all mean.

Again, this is not something obvious, please do read this section, even if you think you know what they mean.

## Release

I'll be using the terminology described in the Summary section of the [«Semantic Versioning 2.0.0»](https://semver.org/spec/v2.0.0.html) document

This is not an enforced standard all throughout software development world, but I find it useful to explain concepts.

- A **major release** is a release where new breaking changes are released. This means that you can expect a software to not be backwards compatible with an old major release.
- A **minor release** is a release where new features are introduced, but behaviour before this release is left untouched. You can expect the software to work just the same before this release, but you'll also have something new to play with.
- A **patch** is a release where bug fixes and security updates have been introduced. You can expect a software to work just the same after such release.

## Stability

Quoting «The American Heritage® Dictionary of the English Language, 5th Edition»:
Stability indicates

> resistance to change

When a software has a stable *major release*, we can assume that said software won't change its behaviour until a next stable *major release*.
In this state, possible updates might include security patches and bug fixes.

An unstable *release* indicates that said software can and probably will change its behaviour and the user SHOULD not rely on its features working the same or even being there at all.

This also means that terms such as *minor release* and *patch* no longer guarantee consistent behaviour.

A software or part of a software can be more or less stable.

Unstable software can be used, stable does not mean better performing or bug free.
To express this very concept we use the term...

## Reliability

Quoting Wikipedia:

> Reliability can be defined as the probability that a system will produce correct outputs up to some given time t

Reliable software is software that allows us to work with less problems due to bugs, crashes or any other kind of undesired behaviour.

Stable software tends to be more thoroughly tested and *patched*, hence, more reliable.

This doesn't imply that unstable software can't be reliable. Feel free to use unstable software if reliable enough.

## Backporting

Quoting Wikipedia:

> Backporting is the action of taking parts from a newer version of a software system or software component and porting them to an older version of the same software

Usually we backport security *patches* and bug fixes to older *stable releases* to improve security and *reliability*.

## Rolling vs Fixed release

### Rolling

When we talk about a rolling release system, we talk about a system that is *unstable* by definition.

A rolling release is a single release that always gets constantly updated with no consistency guarantees unless specified otherwise. 

Rolling release distributions can still be tested and deemed *reliable* enough for home or even production use.

### Fixed

A fixed release system usually gets new *major releases*, *minor releases* and *patches* as defined above and comes with all the guarantees of stability.
(though it might happen that in more *stable* systems, *minor releases* might simply not published and all new features might get introduced in *major releases*)

Bug fixes and security *patches* usually get backported to older *major releases* as long as they are still supported.

Fixed release distros are usually deemed more *reliable* because of the usually extensive testing process each release goes trough before getting published, and because stability usually guarantees that no new issues can be introduced in the same *release*.

---

# Different distros for different needs

First I'll talk about what I'd recommend to newbies, then I'll start discussing about fixed release distributions, then rolling releases, and then immutable distros.

I'll end with my personal favourites.

I won't talk about "gaming" or "development" distros, nor about distros that only ship a slightly modified desktop environment.

Seriously, if there aren't any technical reasons on why a distro should be used, then it is pointless.

## For the newbies

### Linux Mint

Linux Mint has a fixed release model, is based on Ubuntu and features the Cinnamon desktop environment.

Mint's team has all my respect for all the work they do with their desktop environment, Cinnamon, and for trying to create a reliable Ubuntu based system without all the damage that Canonical did with Snap on Ubuntu.

Cinnamon's look and feel can make new users feel right at home and old users will find that having a stable and reliable ubuntu system free of Ubuntu bullshit is nothing short of a pleasant experience.

### Fedora Workstation

With a now fairly extensive support, Fedora Workstation has lately seen an astonishing growth in popularity (and rightfully so!).

On the look and feel side it features a very standard GNOME desktop with almost no special configs by default, however that's not why I'm suggesting it.

Fedora usually ships very up to date software and, while not being as stable as Debian, can still be quite reliable.

The release cycle while being fixed is still faster than many other distributions.

The project is supported by a company while staying a community effort and is basically the testing ground for RedHat Enterprise Linux (RHEL).

*WARNING: There is a small problem with codecs on AMD graphics cards. It's easily fixable but please be aware of this*

## Let's talk fixed

### Debian Stable

There isn't much to say, especially now that Debian started shipping firmware packages in their standard ISOs.

Debian (Stable) is known and appreciated for its extreme stability, however this means that packages, while secure and reliable, are often out of date, so they might not ship the latest features.

Security patches are usually backported from testing repositories.

While being a community project, Debian is considered the "mother" of all distributions, or the "universal operating system", because an enormous amount of distros is actually based on Debian and it can run on basically any kind of hardware.

### Rocky Linux

Born from the ashes of old CentOS, it's basically a community build of RHEL and it's bug-for-bug compatible with it (meaning that behaviour, including bugs, is exactly the same).

It inherits a solid base from RHEL while being driven by a community and a foundation.

Just like Debian, Rocky is extremely stable and not very up to date, and exactly like Debian it's extremely reliable.

*NOTE: It's worth mentioning that similar projects exist such as Alma Linux*

## Rolling downhill

### Arch Linux
Can't avoid naming Arch. I'll be fast I promise.

Arch has extremely up to date software, requires a good amount of maintenance to keep your system working but the repositories are quite large and the Arch User Repository (AUR) has basically every kind of software you might need.

The AUR is basically a community collection of packages where everyone can upload their own.

The system is extremely minimal, the Arch Wiki can help you on any distribution and now that they feature an automated installer it's even faster to install.

### Void Linux
Absolutely love their package manager, XBPS. It's extremely simple while staying rich and powerful.

They don't ship systemd but runit, personally it's not a choice that I really agree with, but it might not even affect you.

They also let you choose between glibc and musl, which is a nice touch, but again, it might not affect you.

Apart from the package manager, a huge selling point is its reliability while being a rolling release distribution.

## Immutable distros

### NixOS
It's a fully reproducible OS, you can build your same exact same system build with a single config file.

Not only that but its package manager, Nix, allows you to build completely reproducible environments on any distribution.

Don't know how to manage your project's dependencies? Perhaps try Nix.

### Fedora Atomic Desktops

Be it Fedora Silverblue, Kinoite, Sway Atomic or Budgie Atomic or any other Fedora Atomic edition, here's how it works.

Any changes you apply to the base system is versioned trough a tool called OSTree, pretty much like git but for operating system versions, and then you can install other packages on Flatpak (default), Toolbx (default) or Distrobox.

This way can roll back to old versions of the base and always have a working version.

### OpenSUSE MicroOS

MicroOS (or whatever name it has now) basically works the same as any Fedora Atomic Desktop, however it uses btrfs snapshots instead of OSTree (which I find really clever).

Just like its Fedora counterpart, you can install packages on Flatpak (default), Toolbx or Distrobox (default).

### VanillaOS 2 (Orchid)

An immutable operating system made by an Italian company called **fabricators Ltd**.

Just like Fedora Atomic and MicroOS, it offers atomic updates trough their own tool called ABRoot.

A detail might remind of NixOS though. Yes you can install updates and system packages trough ABRoot, but to actually edit system files you need to create a container image, possibly trough Vib, Vanilla's very own utility to build container images.

The default shell is in a Distrobox environment called vso-pico and you can manage other environments trough the use of their own tool, apx. In vso-pico you have full access to apt.

Again you can use Flatpak to install other packages.

*WARNING: At the time of writing VanillaOS 2 is still in beta, I'd suggest waiting for the stable release before daily driving it*

## What I'm currently using.

Right now I'm using VanillaOS 2 (Orchid) beta, and I'm having a blast.

However you can easily notice that the distro is indeed still in beta.

Before that I was comfortably using Fedora Workstation, so you might want to take a look at that.

# Did I miss something?

Yes I did. But please let me know anyway! Send me an email if you think this article needs to be updated!

Do also note though, that I didn't insert some distros on purpose, because either I didn't like the project or felt that it was not worth the mention.

```
 _____________ 
< I use mooOS >
 ------------- 
        \   ^__^
         \  (xx)\_______
            (__)\       )\/\
             U  ||----w |
                ||     ||

```
