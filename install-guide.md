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

## Update

Third party dependencies have been merged into the source tree as submodules! If you previously installed RPCSX when you needed `spirv-cross`, `gslang`, or `xbyak`, you should run:

```sh
git pull
git submodule update --recursive --remote
```

## Install

We provide two installation methods:

### Method 1: Linux

#### Install dependencies

- **.deb-based (Ubuntu etc.)**
  Note: git is only needed for Ubuntu 22.04

```sh
sudo apt install build-essential cmake libunwind-dev libglfw3-dev libvulkan-dev vulkan-validationlayers-dev libsox-dev git libasound2-dev nasm g++-14
```

go to [Continued Install.](/wiki/installation/#continued-install)

- **.rpm-based (Fedora etc.)**

```sh
sudo dnf install cmake libunwind-devel glfw-devel vulkan-devel vulkan-validation-layers-devel gcc-c++ gcc sox-devel alsa-lib-devel nasm
```

go to [Continued Install.](/wiki/installation/#continued-install)

- **Arch**
  vulkan-devel is a group, and you should install **all**!

```sh
sudo pacman -S --needed libunwind glfw-x11 vulkan-devel sox git cmake alsa-lib nasm
```

go to [Continued Install.](/wiki/installation/#continued-install)

#### Continued Install

1. Clone the repo.

    ```sh
    git clone --recursive https://github.com/RPCSX/rpcsx && cd rpcsx
    git submodule update --init --recursive
    ```

2. Compile the emulator.

    ```sh
    cmake -B build && cmake --build build -j$(nproc)
    ```

### Method 2: WSL

**Install WSL**
  Run Windows Powershell as Administrator:

```sh
wsl --install
```

Reboot your machine

**Install Ubuntu:**
  Run Windows Powershell

```sh
wsl --install -d Ubuntu
```

Setup user credentials

**Configure Ubuntu and build RPCSX:**
  Add the PPA repository that has the packages we need

```sh
sudo add-apt-repository ppa:oibaf/graphics-drivers
sudo apt upgrade
```

Install Ubuntu package dependencies

```sh
sudo apt install build-essential cmake libunwind-dev libglfw3-dev libvulkan-dev libsox-dev git libasound2-dev nasm g++-14
```

Install WSL specific package dependencies

```sh
sudo apt install pkgconf libasound2-plugins vainfo mesa-va-drivers
```

Add pcm.default pulse to the bottom of the .asoundrc file to configure audio

```sh
echo "pcm.default pulse" > ~/.asoundrc
```

Add ctl.default pulse to the bottom of the .asoundrc file to configure audio

```sh
echo "ctl.default pulse" >> ~/.asoundrc
```

Clone both Vulkan ExtensionLayer and RPCSX Git repositories

```sh
git clone --depth 1 https://github.com/KhronosGroup/Vulkan-ExtensionLayer.git
git clone --depth 1 --recursive https://github.com/RPCSX/rpcsx.git
```

Change directory and compile Vulkan ExtensionLayer

```sh
cd Vulkan-ExtensionLayer
cmake -B build -D UPDATE_DEPS=ON -DCMAKE_BUILD_TYPE=Release
cmake --build build -j$(nproc)
sudo cmake --build build --target install -j$(nproc)
```

Change directory back from Vulkan ExtensionLayer and to RPCSX then compile

```sh
cd ../rpcsx
cmake -B build -DCMAKE_BUILD_TYPE=Release -DCMAKE_CXX_FLAGS_INIT="-march=native" -DCMAKE_CXX_COMPILER=g++-14
cmake --build build -j$(nproc)
sudo cp build/bin/rpcsx /bin
```

Tell Ubuntu to set the VK_LAYER_PATH Environment variable

```sh
echo 'export VK_LAYER_PATH=/usr/local/share/vulkan/explicit_layer.d/:$VK_LAYER_PATH' >> ~/.profile
```

Tell Ubuntu to set the VK_INSTANCE_LAYERS Environment variable

```sh
echo 'export VK_INSTANCE_LAYERS=VK_LAYER_KHRONOS_shader_object' >> ~/.profile
```

Initalize and shutdown the Linux machine

```sh
sudo init 0
```

Wait a few minutes to let Linux shutdown.
  This will not turn off your PC only the virtual Ubuntu distro.

#### ArchWSL

**TODO (under development)**
