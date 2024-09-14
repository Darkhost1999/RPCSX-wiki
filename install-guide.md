---
layout: libdoc/page
title: Installation
order: 2
permalink: /installation/
description: >- 
  For the foreseeable future, installation will require Linux in some form.
---

- TOC
{:toc}

## Update!
Third party dependencies have been merged into the source tree as submodules! If you previously installed RPCSX when you needed `spirv-cross`, `gslang`, or `xbyak`, you should run:
```sh
git pull
git submodule update --recursive --remote
```

## Install

We provide two installation methods:

### Method 1: Linux

#### Install dependencies.

  - **.deb-based (Ubuntu etc.)**
```sh
sudo apt install build-essential cmake libunwind-dev libglfw3-dev libvulkan-dev vulkan-validationlayers-dev libsox-dev git

```
go to [Continued Install.](/wiki/installation/#continued-install)

  - **.rpm-based (Fedora etc.)**
```sh
sudo dnf install cmake libunwind-devel glfw-devel vulkan-devel vulkan-validation-layers-devel gcc-c++ gcc sox-devel git
```
    - Comment out the `text-segment` line in [this file](https://github.com/RPCSX/rpcsx/blob/master/rpcsx-os/CMakeLists.txt#L65), `<repo dir>/rpcsx-os/CMakeLists.txt`
```
# target_link_options(rpcsx-os PUBLIC "LINKER:-Ttext-segment,0x0000010000000000")
```
go to [Continued Install.](/wiki/installation/#continued-install)

  - **Arch**
    - vulkan-devel is a group, and you should install **all**!
```sh
sudo pacman -S --needed git base-devel libunwind glfw-x11 vulkan-devel
```
go to [Continued Install.](/wiki/installation/#continued-install)

#### Continued Install
2. Clone the repo.
```sh
git clone --recursive https://github.com/RPCSX/rpcsx && cd rpcsx
git submodule update --init --recursive
```

3. Compile the emulator.
```sh
mkdir -p build && cd build && cmake .. && cmake --build .
```

4. Create a virtual HDD.
Note: PS4 filesystem is **case-insensitive**.
```sh
truncate -s 512M ps4-hdd.exfat
mkfs.exfat -n PS4-HDD ./ps4-hdd.exfat
mkdir ps4-fs
sudo mount -t exfat -o uid=`id -u`,gid=`id -g` ./ps4-hdd.exfat ./ps4-fs
```

### Method 2: WSL
**TODO (under development)**
#### ArchWSL
**TODO (under development)**
