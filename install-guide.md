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

**Download and install RPCSX:**
  
  ```sh
  wget -O - https://raw.githubusercontent.com/DHrpcs3/rpcsx-setup-wsl/refs/heads/main/rpcsx-setup-wsl.sh | bash
  ```

  - This script will shutdown your Ubuntu distro when complete, This will not turn off your PC only the virtual environment
  
  After the script has completed succesfully relaunch ubuntu through Windows Powershell

  ```sh
  wsl
  ```

  Validate RPCSX installed

  ```sh
  rpcsx --version
  ```

  You are now free to continue onto the [Running RPCSX Guide](/wiki/run/)

  To update RPCSX for WSL in the future you may use this command

  ```sh
  rpcsx-update
  ```

#### ArchWSL

**TODO (under development)**
