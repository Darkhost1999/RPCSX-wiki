---
layout: libdoc/page
order: 1
title: FAQ
permalink: /faq/
description: Frequently Asked Questions about RPCSX.
---

## What is RPCSX?

**A:** RPCSX is an experimental emulator for PS4 games (and later, PS5 games). Development is ongoing.

## Can I play Bloodborne?

Not yet.

## Can I run RPCSX on Windows?

No, currently the project is Linux-only. However, we may support Windows in the future due to popular demand.

### What about the Windows Subsystem for Linux (WSL)?
While WSL allows running Linux on Windows, there are three hurdles to overcome:
1. No confirmed reports of running RPCSX on WSL.
2. The official Vulkan build for WSL lacks required features.
3. No graphics drivers for WSL, resulting in CPU-only rendering.

(*footnote: An experimental shared-memory CUDA driver for WSL exists, intended for TensorFlow/PyTorch. Power users are encouraged to explore using it with Dozen Vulkan.*)

## What is the current state of the project?

The emulator can run test samples and reach the loading screen of [We Are Doomed](https://store.playstation.com/en-us/product/UP2195-CUSA01783_00-WEAREDOOMED00000).  A compatibility table is in progress and will be available when RPCSX can run commercial games.

## Community and Support

Join our [discord server](https://discord.com/invite/WEGamDwZnE) to connect with developers and community members.

## How can I help?

If you'd like to contribute, check our roadmap on the Discord server and explore [the RPCSX GitHub](https://github.com/rpcsx/rpcsx).

## Ways to Contribute

- Submit code changes and improvements
- Assist with documentation and testing
- Share your expertise and feedback
