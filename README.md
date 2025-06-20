# Hackintosh EFI for HP 240 G8 (i3-1005G1, macOS Sequoia)

This repository contains EFI files for running macOS on the HP 240 G8 laptop.

## Hardware Specs

- **Model:** HP 240 G8
- **CPU:** Intel Core i3-1005G1 (10th Gen, Ice Lake)
- **GPU:** Integrated Intel UHD G1 Graphics
- **RAM:** 8GB DDR4 3200MHz
- **Storage:** Samsung PM991 256GB NVMe SSD (see Status for more info)
- **Display:** Generic 14" 1366x768
- **Wi-Fi/Bluetooth:** Non-stock Intel AX210 (Using itwlm and IntelBluetoothFirmware from OpenIntelWireless)
- **Audio:** Realtek ALC236
- **Ethernet:** Realtek GBE Family Controller
- **Touchpad:** ELAN (don't use VoodooI2CELAN otherwise it won't work.)

## Hackintosh Details

- **macOS Version:** macOS Sequoia 15.5
- **Bootloader:** 1.0.4
- **SMBIOS:** MacBookPro 16,2 (for compatibility with the next macOS Version, you may use MacBookAir 9,1 if Sequoia or older is your target)

## Status

- **Working:** Graphics acceleration, Audio (Built-in Speakers and 3.5mm Jack), Battery status, USB ports, Sleep, Ethernet, Touchpad, Camera and Microphone.
- **Works, but needs manual interaction:** Samsung PM991 NVMe Drive (if you don't have this drive, you probably do not need to do this): due to drivers compability using the NVMeFix kext, getting the NVMe Drive to work is a bit complicated, but it essencially requires you to first install macOS in an external drive, until it asks for region settings, and only then clone the external drive to the internal one. This is an "fix", but when disk usage is too high, the write and read speed decreases substantially. If you don't use this fix and you only have the NVMeFix kext, the NVMe drive can heat up and even get damaged.
- **Not Working:** AirDrop (requires AirPortitwlm), Hardware DRM-Protected Content (Apple Music, Apple TV+ and using Safari to watch Netflix, Prime or others).
- **Not Tested:** HDMI Port (Audio & Video).

## What's Included

- Pre-configured EFI files for a smooth Hackintosh installation on the HP 240 G8.
- Currently supports macOS Sequoia.
- REMEMBER TO CHANGE SMBIOS SERIAL NUMBER OR YOU WON'T HAVE ISERVICES!

## Who is this for?

Anyone looking to get macOS running on this specific HP model or similar.

## Coming Soon

I plan to add:
- A detailed guide and troubleshooting tips.
- Notes on kexts, BIOS settings, and post-install tweaks.
  
---

*Feel free to contribute or open issues if you have questions or suggestions!*
