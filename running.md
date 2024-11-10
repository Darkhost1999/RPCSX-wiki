---
layout: libdoc/page
title: Running RPCSX
order: 2
permalink: /run/
description: >-
  After installing RPCSX, here's how you start testing it.
---

- TOC
{:toc}

## Prerequisites

You will need a decrypted dump of the PlayStation 4 console firmware, **OBTAINED LAWFULLY, FROM YOUR OWN PS4 CONSOLE**.

Compatible versions:
- 5.05
- 9.0
- 11.0

## Help
- See the Commands of `rpcsx` (`-h` argument)
- Join the [Discord](https://discord.com/invite/WEGamDwZnE).

## Booting games:

```sh
./rpcsx --mount /path/to/firmware/md0/ /  --mount /path/to/game/app0 /app0 /app0/eboot.bin [optional args, without brackets]
```

## Booting the firmware:

```sh
./rpcsx --system --mount /path/to/firmware/md0/ / /mini-syscore.elf
```

- Use optional argument `--safemode` for booting in safe mode.

## Global optional args
- Log a segfault: `--trace`
- Log to a text file: add `&> log.txt` at the end of the whole command before pressing enter
