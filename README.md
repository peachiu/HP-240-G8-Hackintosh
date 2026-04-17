# Hackintosh EFI for HP 240 G8 (i3-1005G1)
### Supported Versions: Ventura, Sonoma, Sequoia & Tahoe

This repository contains pre-configured EFI files for running macOS on the HP 240 G8 laptop. It has been tested and refined for stability across multiple macOS versions, including the latest macOS Tahoe.

> [!WARNING]
> This README is currently being updated. Use the files in the `EFI's` folder corresponding to your target macOS version.

## 💻 Hardware Specifications

- **Model:** HP 240 G8
- **CPU:** Intel Core i3-1005G1 (10th Gen, Ice Lake)
- **GPU:** Integrated Intel UHD Graphics G1
- **RAM:** 8GB DDR4 3200MHz
- **Storage:** Samsung PM991 256GB NVMe SSD (See status, down below, for details)
- **Display:** 14" (1366x768)
- **Wi-Fi/Bluetooth:** Intel AX210 (Non-stock)
  - *Ventura:* Uses `AirportItlwm`
  - *Sonoma / Sequoia / Tahoe:* Uses `itlwm` + `HeliPort` (Recommended for best stability)
- **Audio:** Realtek ALC236 (layout-id: 55)
- **Ethernet:** Realtek GBE 8111 Family Controller
- **Touchpad:** ELAN (I2C) - *Do not use VoodooI2CELAN as it causes conflicts.*

## 🛠️ Hackintosh Configuration

- **Tested macOS Versions:** 
  - ✅ **macOS Tahoe (26.1)** - [BETA 2.0.0] - (OpenCore 1.0.7 DEV)
  - ✅ **macOS Sequoia (15.5)** - [RELEASE 1.0.0] - (OpenCore 1.0.4)
  - ✅ **macOS Sonoma (14.x)** - [RELEASE 1.0.0] - (OpenCore 1.0.4)
  - ✅ **macOS Ventura (13.7.6)** - [RELEASE 1.0.0] - (OpenCore 1.0.4)

- **SMBIOS:** 
  - `MacBookAir9,1` (Recommended for Ice Lake compatibility in macOS Sequoia and below)
  - `MacBookPro16,2` (Used in Tahoe EFI for broader compatibility)

> [!IMPORTANT]
> **SMBIOS values (Serial, MLB, UUID, ROM) have been cleared from all config.plist files for privacy.** 
> You **MUST** generate your own unique identifiers using [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) or [OCAT](https://github.com/ic005k/OCAuxiliaryTools) before attempting to boot, otherwise iMessage and other iCloud services will not work.


## 📊 Status(#status)

### ✅ Working
- Graphics Acceleration (Intel UHD G1)
- Audio (Built-in Speakers, 3.5mm Jack, Microphone)
- Battery Status & Power Management
- USB Ports (USB 3.0 / USB-C mapped via USBToolBox)
- Sleep / Wake
- Ethernet (Realtek 8111)
- Touchpad (ELAN - Multi-touch gestures)
- Camera & Microphone
- Keyboard (With PT-PT Layout support)

### ⚠️ Partial / Needs Manual Work
- **Samsung PM991 NVMe:** This drive has compatibility issues with the native NVMe driver.
  - **Workaround:** Install macOS on an external drive first, then clone the partition to the internal drive.
  - **Performance:** High disk usage may cause speed drops. `NVMeFix.kext` is included to mitigate heating.
- **AirDrop/Continuity:** 
  - Works natively on Ventura with `AirportItlwm`.
  - Limited/Experimental on Sequoia/Tahoe (Requires `itlwm` or specific beta builds of `AirportItlwm`).

### ❌ Not Working
- **DRM-Protected Content:** Hardware DRM (Streaming services on Safari, Apple TV+, etc.) does not work on Intel IGPU. Use Chrome/Firefox for DRM Software protected web streaming.
- **HDMI Audio/Video:** Does not work. Since Apple removed HDMI from MacBooks and introduced video via USB-C/Thunderbolt on later models such as the one that have a 10th generation Intel Ice Lake processor.

## 🚀 Getting Started

1. **EFI Selection:**
   - For **Tahoe**, use the files in `EFI's/BETA 2.0.0/macOS Tahoe - nov 2025`
> [!WARNING] 
> This is a beta version and may not work correctly.
   - For **Sequoia/Sonoma/Ventura**, use the corresponding folders in `EFI's/1.0.0`
> [!WARNING] 
> New update versions are to come soon when i'm able to test them.
2. **SMBIOS:** Remember to generate your own `SystemSerialNumber`, `MLB`, and `SystemUUID` using [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) or [OCAT](https://github.com/ic005k/OCAuxiliaryTools).
3. **BIOS Settings:**
   - **Secure Boot:** Disabled
   - **Fast Boot:** Disabled
   - **SATA Mode:** AHCI
   - **VT-d / VT-x:** Enabled

## ⌨️ Extra Features
- A custom **PT-pt HP Keyboard Layout** is available in the `Keyboard Layouts` folder for better compatibility with the physical keyboard layout of this laptop in the european portuguese layout.

---
*Feel free to open issues if you have questions or suggestions!*

