# lenovo-thinkpad-l430
![lenovo thinkpad l430](https://res.cloudinary.com/dk0053zbe/image/upload/v1604047563/wp_lkr4kr.jpg)

## spesifikasi :
- Bootloader Opencore 0.6.3
- processor core i3 3120M (Ivy Bridge)
- vga intel hd 4000
- audio alc269 layout-id 28
- Ethernet RTL8168E-VL
- WLAN INTEL Centrino Advance 6025
- Intel 7 Series Chipset
- Touchpad ELAN

## Working :
- iGpu intel HD 4000
- USB port
- Sound Alc269
- Touchpad
- etc
- Sleep
- shotdown
- Restart
- SMBIOS MacBookPro10,2 ( Ivy Bridge(M) )
- Brightness, Fn + p (brightness up) and Fn + k (brightness down)
## Not Working :
- VGA port
- WLAN not support by hackintos

## Not Test :
- Display Port

## Patch SSDT:
- PNLF (Fix Brightness)
- PM (CPU power management)
- EC (Fixes the embedded controller)
- XOSI (Makes all _OSI calls specific to Windows work for macOS (Darwin) Identifier. This may help enabling some features like XHCI and others.)
- IMEI (Needed to add a missing IMEI device on Ivy Bridge)
- HPET (Fixing IRQ Conflicts) https://dortania.github.io/Getting-Started-With-ACPI/Universal/irq.html
- SBUS-MCHC fix SMBUS

## Kext Version Control
- AppleALC              : V1.5.5 (RELEASE)
- Lilu                  : V1.5.0 (RELEASE)
- RealtekRTL8111        : V2.3.0 (RELEASE)
- VirtualSMC            : V1.1.9 (RELEASE)
- VoodooPS2Controller   : V2.1.9 (RELEASE)
- WhateverGreen         : V1.4.5 (RELEASE)
- YogaSMC               : V1.3.0 (RELEASE)
- USBMap                : Generated (CUSTOM)
## Patch Log:
- 20-10-2020 fixing Checksum CMOS Failur on booting with patch RTC, Set Kernel > Quirk > DisableRtcChecksum as True
- 30-10-2020 Fixing iGPU performance with add Under DeviceProperties -> Add -> PciRoot(0x0)/Pci(0x2,0x0)
```txt
igfxfw | Data | <02 00 00 00>
```
- 30-10-2020 Fixing SMBUS https://dortania.github.io/Getting-Started-With-ACPI/Universal/smbus-methods/manual.html#finding-the-acpi-path
- 02-11-2020 add YogaSMC for Allow syncing SMC keys like sensors reading and battery conservation mode,Currently Yoga, IdeaPad and ThinkPad series are supported. https://github.com/zhen-zen/YogaSMC 
- 04-11-2020 change ApplePS2SmartTouchPad.kext to VoodooPS2Controller V2.1.8 Fixed dynamic coordinate refresh for ELAN v3 touchpads https://github.com/acidanthera/VoodooPS2/releases/tag/2.1.8
- 13-11-2020 fix usb map and rename  EHC1 to EH01, EHC2 to EH02 for detail see https://dortania.github.io/OpenCore-Post-Install/usb/system-preparation.html
- 09-12-2020 Downgrade opencore 0.6.4 to 0.6.3 
- 27-12-2020 Fixing output display port, white screen when charger pluged

## Update Bootloader Log
- 09-12-2020 Update bootloader opencore 0.6.2 to 0.6.4
- 09-12-2020 Downgrade opencore 0.6.4 to 0.6.3 , ditemukan bug yg fatal, saat booting muncul error OC : failed load condiguration
