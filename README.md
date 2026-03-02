# OpenCore EFI for the HP Victus 16

:information_source: **The current version of the EFI is only compatible with macOS Ventura! Any other versions are UNTESTED!**

<br>

[![OpenCore](https://img.shields.io/badge/OpenCore-1.0.6-lightblue.svg)](https://github.com/acidanthera/OpenCorePkg)

:warning: **DISCLAIMER:**
THIS IS NOT A GUIDE!
\
\
This is simply an EFI backup for the HP Victus 16. Only use this EFI if you have the exact same model. 
\
\
<br>

## :computer: Hardware:

| **Category** | **Component**                                                                    |
| ------------ | -------------------------------------------------------------------------------- |
| **CPU**      | AMD Ryzen 5 5600H 6-Core Processor                                               |
| **GPU**      | AMD Radeon RX Vega 7                                                             |
| **RAM**      | 16GB DDR4 3200MHz                                                                |
| **SSD**      | Crucial OEM SSD                                                                  |
| **Wi-Fi/BT** | Realtek RTL8852AE                                                                |
| **Ethernet** | Realtek RTL8111                                                                  |
| **Audio**    | Realtek ALC245 (layout-id=11)                                                    |

## :white_check_mark: Working:
- [x] CPU power management (still problematic due to AMD, but works fine)
- [x] Graphics acceleration (Chromium based hw still have issue. See also https://chefkiss.dev/applehax/nootedred/#chrome-chromium-based-browsers-and-apps-like-sublime-text-cause-graphical-artefacts-amongst-other-problems)
- [x] Keyboard & Trackpad
- [x] USB ports
- [x] Ethernet
- [x] Audio (internal speakers, 3.5mm headphone jack)
- [x] iCloud & App Store

## :question: In-between:
- [x] HDMI video & audio output (not tested)
- [x] Webcam (I don't even realise am I use webcam)
- [x] iMessage & Face Time (I can't use these android so i can't tested)

## :no_entry_sign: Not working:
- [x] Virtualization (due to the lack of AMD-V support in macOS)
- [x] Sleep & Wake (will be fixing in next versions of this EFI)
- [x] Nvidia dGPU (current MacOS don't like him)
- [x] Wi-fi & Bluetooth (Realtek cards not supported)

## :closed_lock_with_key: SMBIOS

You will need to generate your own SMBIOS and edit the config, since it is required to boot macOS **at all**. 
The HP Victus 16 works best with the MacBookPro16,3 SMBIOS, but if a different one that works better is discovered, we'll update the repo.
Use [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) to generate your own PlatformInfo values and then copy them to the related path in:

- Config.plist -> PlatformInfo -> Generic

## BIOS setup:

- Disable TPM and fTPM (optional) set the assigned VRAM via [SmokeLessUMAF](https://github.com/DavidS95/Smokeless_UMAF) to 1G at minimum, 2G is recommended. 
- Secure boot should also be off.

## Credits:

[**Acidanthera**](https://github.com/acidanthera) for [OpenCore](https://github.com/acidanthera/OpenCorePkg)

[**Dortania**](https://dortania.github.io/getting-started/) for their guide

[**lzhoang2801**](https://github.com/lzhoang2801/OpCore-Simplify) for providing the essential EFI patches and structures for this build

[**ic005k**](https://github.com/ic005k/OCAuxiliaryTools) for the graphical configuration and database management suite

[**DavidS95**](https://github.com/DavidS95/Smokeless_UMAF) for locked down BIOS control 

[**CorpNewt**](https://github.com/corpnewt) for [ProperTree](https://github.com/corpnewt/ProperTree) and [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)

[**AMD-OSX**](https://github.com/AMD-OSX/AMD_Vanilla) for AMD Kernel Patches

[**Gemini**](gemini.google.com) for providing step-by-step guidance, troubleshooting, and configuration assistance throughout the Hackintosh process

[**Apple**](http://apple.com/) for obvious reasons
