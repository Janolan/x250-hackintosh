# X250 Hackintosh (macOS 10.14.x)

This is a guide to set up the Lenovo Thinkpad X250 as a 99% working hackintosh.

## Introduction

Thinkpad X250 Hackintosh configuration. This repository contains the following folders:

- `EFI`: put this in your EFI partition in `EFI` folder, including `Boot` and `CLOVER` sub-folders,
- `Kexts`: kexts to install in `/Library/Extensions` on your local drive once macOS has been installed.

It's a `99.99%` working hackintosh. What doesn't work (yet):

- Trackpad
- Trackpad Buttons
- Wifi (use a USB Wifi Dongle or replace the Wifi Card with a DW1560)
- Card Reader

## Setup

### Bios Settings

The bios must be properly configured prior to installing MacOS.

In `Security` menu, set the following settings:

- `Security > Security` Chip: must be **Disabled**,
- `Memory Protection > Execution Prevention`: must be **Enabled**,
- `Virtualization > Intel Virtualization Technology`: must be **Disabled**,
- `Internal Device Access > Bottom Cover Tamper Detection`: must be **Disabled**,
- `Anti-Theft > Current Setting`: must be **Disabled**,
- `Anti-Theft > Computrace > Current Setting`: must be **Disabled**,
- `Secure Boot > Secure Boot`: must be **Disabled**.

In `Startup` menu, set the following options:

- `UEFI/Legacy Boot`: **Both**,
- `UEFI/Legacy Priority`: **UEFI First**,
- `CSM Support`: **Yes**.

Now you can go through the install. 

### Bootable USB Drive

The guide [how to create a Mojave USB Installer Drive](https://internet-install.gitbook.io/macos-internet-install/) explains how to create a USB flash drive to install MacOs on your X250. Follow it up to the point where you are supposed to download
"the latest Clover LZMA from Dids' repo" at the beginning of the section "Clover and friends [part 1]...".

### Copy EFI Folder to USB

Copy the content of the `EFI` folder provided in my repo onto your USB flash drive `EFI` partition. The EFI partition is usually hidden. Use [Clover Configurator](https://mackie100projects.altervista.org/download-clover-configurator/) to mount the EFI partition of your flash drive on your mac (it appears as a disk on the desktop once done). On Windows or Linux it shouldn't be hidden.

### Install macOS

Install macOS by booting on the USB key. It takes about 30min. The computer will restart multiple times. Make sure to select `Install macOS ...` each time. Once installed, choose to boot from local drive in Clover boot menu.

### What's next?

To finish the setup, you need to make your local drive bootable (right now you are still using the Clover boot from your USB installer to boot your system:

- **Copy EFI** folder from USB flash drive to local drive `EFI` partition (like you did for the USB installer). Use [Clover Configurator](https://mackie100projects.altervista.org/download-clover-configurator/) to mount it.
- **Install Kexts**: install kernel extensions provided by `Kexts` from this repository into `/Library/Extensions`. Use this guide to [properly install the kexts.](https://www.tonymacx86.com/threads/guide-installing-3rd-party-kexts-el-capitan-sierra-high-sierra-mojave.268964/)]

You're almost done! Reboot and enjoy macOS on your Thinkpad X250.

## Miscellaneous

### SSD Enable Trim

If you Sata ssd hasn't trim enabled, run the following command from the *Terminal* to enable it:

```
sudo trimforce enable
```
