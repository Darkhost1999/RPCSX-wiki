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

## How to run samples and games

You will need a decrypted dump of the console firmware, **OBTAINED LAWFULLY, FROM YOUR OWN PS4 CONSOLE**.

Compatible versions:
- 5.05
- 9.0
- 11.0

## Help
See the Commands of `rpcsx-os` (`-h` argument), or join the [Discord](https://discord.gg/t6dzA4wUdG).

## Booting games: 
```sh
rm -rf /dev/shm/rpcsx-* && ./rpcsx-gpu
```
**WAIT** for it to say `waiting for dmem0`
```sh
rpcsx-os --mount /path/to/firmware/md0/ /  --mount /path/to/game/app0 /app0 /app0/eboot.bin [optional args, without brackets]
```
## Booting the firmware:
```sh
./rpcsx-os --system --mount /path/to/firmware/md0/ / /mini-syscore.elf
```
- Use optional argument `--safemode` for booting in safe mode.

## Global optional args
- Log a segfault: `--trace`
- Log to text file: add `&> log.txt` at the end of the whole command before hitting enter
