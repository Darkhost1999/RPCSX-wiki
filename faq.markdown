---
layout: libdoc/page
order: 1
title: FAQ
permalink: /faq/
description: Frequently Asked Questions about RPCSX.
---

## What is this?

**A:** RPCSX is an experimental emulator for PS4 games (and later, PS5 games). Development is ongoing.

## Can I play Bloodborne? 

Not yet.

## Can I run RPCSX on Windows?

No. The current scope of the project is Linux-only. This may change in future, as the overwhelming majority of the user-base is on Windows.

### What about the WSL?
The Windows Subsystem for Linux ("WSL") is a Windows feature that virtualizes (or hypervises) a Linux distro inside (or alongside) your Windows intstallation. Three hurdles exist:
1. Currently, there are no confirmed reports of running RPCSX on WSL. 
3. The official Vulkan build for WSL does not support the features required.
2. There are no graphics drivers for the WSL, so rendering is CPU-only. (*footnote: there's an experimental shared-memory CUDA driver for WSL intended for use with TensorFlow/PyTorch. Any power users that want to kludge that together with Dozen Vulkan, please do so.*)

## What is the current state of the project?

The emulator can run a few test samples, and can get to the loading screen of [We Are Doomed](https://store.playstation.com/en-us/product/UP2195-CUSA01783_00-WEAREDOOMED00000). A compatibility table is in the works, and will likely arise when RPCSX is able to properly run commercial games.

## Where can I get in touch with developers and community members?

See [the project's discord server](https://discord.com/invite/mx8FbxN5).

## How can I help?

If you'd like to contribute, our roadmap is in the server above, and [the project is on GitHub](https://github.com/rpcsx/rpcsx).