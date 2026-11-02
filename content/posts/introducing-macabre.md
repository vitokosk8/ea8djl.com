---
title: "MACabre: giving Layer 2 the attention it deserves"
date: 2026-11-02
tags: ["networking", "security", "layer2", "mikrotik", "open-source"]
draft: false
---

We pour years into hardening Layer 3. We filter prefixes, sign
routes, argue about RPKI over coffee. And then someone walks into a
meeting room, plugs in a laptop, and the switch happily hands them
the keys to the kingdom. Layer 2 is the floor nobody looks at until
they trip over it.

So I started building **MACabre**.

## So what is it?

MACabre (yes, *MAC* + *macabre* — I'm not sorry) is an open-source
Layer 2 auditing suite in Python, with a PySide6 desktop GUI and
Scapy doing the dirty work underneath. Point it at your own lab,
pick an attack from the menu, and watch how your switches, bridges
and access ports hold up.

If you've ever used [Yersinia](https://github.com/tomac/yersinia),
you'll feel right at home — it's the inspiration behind the whole
thing. MACabre isn't a fork, though: it's a fresh codebase on a
modern Python stack, so it's actually pleasant to extend and keep
alive.

## Two jobs, one tool

I'm building MACabre to wear two hats:

- **Real auditing.** Testing the resilience of networks I own or am
  authorised to test — the access edge that usually gets ignored.
- **Teaching.** This is the part I'm most excited about. I want it
  to be a visual aid in the classroom, something to *show* instead of
  just describe. When I run the **MTCSE** and **MTCSWE** MikroTik
  official courses, it's one thing to say "DHCP starvation drains
  the pool" and quite another to launch it live and then walk
  through the RouterOS features that shut it down.

Because that's the whole point: every attack in MACabre is paired,
in my head, with its defence. Understanding the attack is how you
learn to stop it.

## The roadmap, roughly

Kicking off with the Layer 2 classics — DHCP pool exhaustion first,
then LLDP, CDP and STP/BPDU. Alongside the desktop app there's a
console-only build that runs as a container, even directly on
MikroTik RouterOS devices, so you can test from a real spot in the
topology instead of a laptop in the corner.

## Come say hi

It lives on GitHub as
[vitokosk8/MACabre](https://github.com/vitokosk8/MACabre), Apache
2.0, with an early `v0.1.0` preview up. It's very much day one —
issues, ideas and "have you thought about…" are all welcome.
