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

You will need a decrypted dump of the PlayStation 4 or PlayStation 5 console firmware, **OBTAINED LAWFULLY, FROM YOUR OWN PS4 OR PS5 CONSOLE**.

## Help

- See the Commands of `rpcsx` (`-h` argument)
- Join our [Discord](https://discord.com/invite/WEGamDwZnE) for support and discussion.

## Booting games

```sh
rpcsx --fw <path to fw> games/CUSA##### [optional args, without brackets]
```

## Booting the firmware

```sh
rpcsx --fw <path to fw>
```

- Use the optional argument `--safemode` for booting in safe mode.

## Global optional args

- Log a segfault: `--trace`
- Log to a text file: add `&> log.txt` at the end of the whole command before pressing enter

## Booting Samples

At the time of writing, booting samples requires advanced mounting commands for firmware and path to sample. Simplified commands will not work.

```sh
./rpcsx --mount  "<path to fw>/system" "/system" --mount "<path to 'game' root>" /app0 /app0/some-test-sample.elf [<args for test elf>...]
```
