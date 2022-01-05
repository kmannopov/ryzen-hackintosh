# OpenCore EFI for AMD Ryzen Hackintosh

[![macOS version](https://img.shields.io/badge/macOS-12.0.1-informational.svg)](https://www.apple.com/macos)
[![OpenCore version](https://img.shields.io/badge/OpenCore-0.7.5-informational.svg)](https://github.com/acidanthera/OpenCorePkg)

## Description:
This is a working EFI configuration for those who want to install MacOS on their Ryzen systems, but don't want to go through the hassle of creating a new OpenCore configuration. The config has only been tested on the hardware listed below.
I would highly suggest generating a unique SMBIOS and editing the config.plist file to update the old values. A guide on how to do that can be found [here](https://dortania.github.io/OpenCore-Install-Guide/AMD/zen.html#platforminfo).

## Verified Specification

| **Component**    | **Model**                                   |
| ---------------- | ------------------------------------------- |
| CPU              | AMD Ryzen 5 1400 @ 3.5GHz                   |
| Motherboard      | MSI B350M Bazooka                           |
| RAM              | 2 x 8GB Corsair Vengeance RGB PRO @ 3200MHz |
| GPU              | MSI RX 580 ARMOR 8GB OC                     |
| Audio Chipset    | ALC-892                                     |
| Ethernet         | Realtek RTL8111                             |
| WiFi & Bluetooth | Intel Dual Band Wireless AC 3165            |
| OS Disk (NVMe)   | WD Blue SN550 512GB NVME SSD                |

**macOS version**: 12.0.1 (21A559) \
**OpenCore version**: 0.7.5

## What is working:

- Everything besides what is mentioned below

## What is not working:

- 3.5mm Microphone jack (you need to use a Bluetooth/USB microphone, or buy a 3.5mm to USB adapter). Alternatively, you can use VoodooHDA instead of AppleALC but there is a drop in audio quality.
- Virtual Machines relying on AppleHV
    This includes VMWare, Parallels, Docker, Android Studio, etc
    VirtualBox is the sole exception as they have their own hypervisor
    VMware 10 and Parallels 13.1.0 do support their own hypervisor, however using such outdated VM software poses a large security threat

## Known Bugs:
- The inital software update check for MacOS causes the keyboard to stop working (unplugging and plugging the keyboard back in fixes it). The software update check can be disabled in System Preferences -> Software Update -> Advanced -> Check for updates.
