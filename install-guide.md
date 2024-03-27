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

There are currently two methods to install RPCSX:
### Method 1: Linux

1. Install dependencies.
#### .deb-based (Ubuntu etc.)
```sh
sudo apt install build-essential cmake libunwind-dev libglfw3-dev libvulkan-dev vulkan-validationlayers-dev spirv-tools glslang-tools libspirv-cross-c-shared-dev
```
go to [Continued Install.](/wiki/installation/#continued-install)
#### .rpm-based (Fedora etc.)
- Install traditional dependencies.
```sh
sudo dnf install cmake libunwind-devel glfw-devel vulkan-devel vulkan-validation-layers-devel spirv-tools glslang-devel gcc-c++ gcc spirv-tools-devel xbyak-devel
```
- Install `spirv-cross`.
```sh
git clone https://github.com/KhronosGroup/SPIRV-Cross && cd SPIRV-Cross && mkdir build && cd build && cmake .. && cmake --build . && sudo make install
```
- Comment out the `text-segment` line in [this file](https://github.com/RPCSX/rpcsx/blob/master/rpcsx-os/CMakeLists.txt#L65), `<repo dir>/rpcsx-os/CMakeLists.txt`
```
# target_link_options(rpcsx-os PUBLIC "LINKER:-Ttext-segment,0x0000010000000000")
```
go to [Continued Install.](/wiki/installation/#continued-install)

#### Arch
- Install traditional dependencies.
```sh
sudo pacman -S libunwind glfw-x11 vulkan-devel glslang
```
- Pull `spirv-cross` from the AUR. **Skip the first line if you have `yay` already.**
```sh
sudo pacman -S --needed git base-devel && git clone https://aur.archlinux.org/yay.git && cd yay && makepkg -si
```
```sh
yay -S spirv-cross
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
Note that the PS4 filesystem is **case-insensitive**.
```sh
truncate -s 512M ps4-hdd.exfat
mkfs.exfat -n PS4-HDD ./ps4-hdd.exfat
mkdir ps4-fs
sudo mount -t exfat -o uid=`id -u`,gid=`id -g` ./ps4-hdd.exfat ./ps4-fs
```

### Method 2: WSL
**TODO**
#### ArchWSL
**TODO**
