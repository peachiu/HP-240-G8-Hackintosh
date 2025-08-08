# Hackintosh EFI for HP 240 G8 (i3-1005G1, macOS Ventura and macOS Sequoia) - Outdated, needs reviewing.

This repository contains EFI files for running macOS on the HP 240 G8 laptop.

## Hardware Specs

- **Model:** HP 240 G8
- **CPU:** Intel Core i3-1005G1 (10th Gen, Ice Lake)
- **GPU:** Integrated Intel UHD G1 Graphics
- **RAM:** 8GB DDR4 3200MHz
- **Storage:** Samsung PM991 256GB NVMe SSD (see Status for more info)
- **Display:** 14" - 1366x768
- **Wi-Fi/Bluetooth:** Non-stock Intel AX210 (Using itlwm and IntelBluetoothFirmware from OpenIntelWireless for macOS Sequoia and Airportitlwm for macOS Ventura)
- **Audio:** Realtek ALC236
- **Ethernet:** Realtek GBE 8111 Family Controller
- **Touchpad:** ELAN (don't use VoodooI2CELAN otherwise it won't work.)

## Hackintosh Details

- **Tested macOS Versions:** macOS Sequoia 15.5 and macOS Ventura 13.7.6
- **Opencore Bootloader Version:** 1.0.4
- **SMBIOS:** MacBookPro 16,2 (for compatibility with macOS Tahoe in the future, you may use MacBookAir 9,1 if Sequoia or older is your target)

## Status

- **Working:** Graphics acceleration, Audio (Built-in Speakers and 3.5mm Jack), Battery status, AirDrop on Ventura, USB ports, Sleep, Ethernet, Touchpad, Camera and Microphone.
- **Works, but needs manual interaction:** Samsung PM991 NVMe Drive (if you don't have this drive, you probably do not need to do this): due to drivers compability using the NVMeFix kext and getting the NVMe Drive to work is a bit complicated, but it essencially requires you to first install macOS in an external drive, until it fully installs and the oobe starts, then clone the external drive partition to the internal one. This is an "fix", but when disk usage is too high, the write and read speed decreases substantially. If you don't use this fix, have the NVMeFix.kext installed and you use an different drive for the install, the NVMe drive can heat up and even get damaged.
- **Not Working:** AirDrop on Sequoia (requires AirPortitwlm), Hardware DRM-Protected Content on both macOS Versions (Apple Music Lossless, Apple TV+ and using Safari to watch Netflix, Prime or others).
- **Not Tested:** HDMI Port (Audio & Video).

## What's Included

- Pre-configured EFI files for a smooth Hackintosh installation on the HP 240 G8.
- Currently supports macOS Sequoia.
- REMEMBER TO CHANGE SMBIOS!

## Who is this for?

Anyone looking to get macOS running on this specific HP model or similar hardware.

## Coming Soon

I plan to add:
- A detailed guide and troubleshooting tips.
- Notes on kexts, BIOS settings, and post-install tweaks.
  
---

*Feel free to contribute or open issues if you have questions or suggestions!*
