---
title: The year is about to end, I feel lonely and decided to write a bit about Linux rootkits
author: BinaryBunny
date: '2021-12-31'
tags:
  - rootkits
  - linux
  - end of the year
---

If you're from Brazil, you may have seen [all those news about a massive flood happened to the brazilian state of Bahia](https://edition.cnn.com/2021/12/28/americas/brazil-bahia-flooding-intl/index.html). It happens that I'm actually from there and a few people from my family got homeless due to the flood. It's 3 AM here at the time of writing and I feel lonely and kind of useless on dealing with the entire situation... So, I decided to host this blog up and write this very post about Linux rootkits.

---

## A boring "what is a rootkit?" section

Wikipedia defines a rootkit as:

> "A rootkit is a collection of computer software, typically malicious, designed to enable access to a computer or an area of its software that is not otherwise allowed (for example, to an unauthorized user) and often masks its existence or the existence of other software."

As one would expect, most rootkits runs on ring 0 (same level of privileges of a kernel). User-mode rootkits are often made however, using fun tricks such as [`LD_PRELOAD`](https://stackoverflow.com/questions/426230/what-is-the-ld-preload-trick). But here we're going straight forward to the kernel-mode ones.

## LKM rootkits and the usual attack-chain

Ring 0 rootkits are written as *Linux Kernel Modules* (LKM for short), which allows an attacker to easily hook syscalls for example, but requires that same attacker to have root privileges in the victim's system for load it.

With that in mind, attackers usually perform social engineering techniques or even privilege-scalation exploits to gain victim's root password.

---

Quick note of a random idea I just got.

One's attack-chain could have both user-mode and kernel-mode rootkits. The former could be used to hook `sudo` (example) for stealing root password and using it to load the latter.

---

## What is a ring 0 rootkit capable of?

In short, *almost everything*. In fact, it's hard to think of something kernel-mode rootkits aren't capable of as they run as part of the kernel.

## Why are you writing all of this????

*I know, I know*. Everything I wrote until far didn't go in-depth on the topic.

To be honest, this post has been written just for being *an indirect introduction to me and my blog*. An attentive reader may have got some basic knowledge of my own personality *just from this very written sentences*.

I actually *planned* talking in-depth about LKM rootkits and stuff but I'm honestly feeling bad and just noted that, if I'm not going depth in the subject, then everything I wrote is basically useless as the same message has been said a hundred times before with different sentences each: It's just like fooling you around and not contributing at all with knowledge or even teaching you something you didn't know, and *I don't like doing that*.

## A frustrating conclusion

Sorry for basically wasting your time writing about rootkits, just to have some weird crisis and venting. I don't know yet if this blog is about technology or my feelings (maybe both?).

For those who made it up until this far, I plan writing more posts about linux rootkits in the future but going actually in-depth and not venting in the middle of it.

Thank y'all so much. :purple_heart:
