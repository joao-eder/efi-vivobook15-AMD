# OpenCore EFI: Asus Vivobook 15 (M1502IA, AMD Ryzen 5 4600H)

OpenCore EFI for the **Asus Vivobook 15 M1502IA-EJ251** running macOS on AMD, with integrated Vega graphics accelerated by NootedRed.

## Hardware

| Component | Model |
|---|---|
| CPU | AMD Ryzen 5 4600H |
| iGPU | Radeon Vega 6 |
| RAM | 20 GB |
| Storage | 256 GB NVMe |
| Wi-Fi / Bluetooth | Broadcom BCM94360CS2 |
| Audio | Realtek ALC256 |
| Keyboard | PS/2 |
| Touchpad | I2C HID |

## Main kexts

| Purpose | Kexts |
|---|---|
| Base | Lilu, VirtualSMC, RestrictEvents, FeatureUnlock, AMFIPass |
| CPU (AMD) | AMDRyzenCPUPowerManagement, SMCAMDProcessor, AppleMCEReporterDisabler |
| Graphics | NootedRed, SMCRadeonSensors |
| Audio | AppleALC |
| Input | VoodooPS2Controller, VoodooInput, VoodooI2C, VoodooI2CHID, BrightnessKeys |
| Battery / sensors | SMCBatteryManager, SMCLightSensor, ECEnabler |
| Wi-Fi | IO80211FamilyLegacy, IOSkywalkFamily |
| Storage / USB | NVMeFix, USBMap, USBWakeFixup |

## Before you boot

The EFI ships **without SMBIOS** (`EFI NO SMBIOS.zip`). Before using it:

1. Generate serial, MLB and UUID with [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) (model `MacBookPro16,3`) and fill them into `config.plist`.
2. Generate the ACPI tables for your machine with [SSDTTime](https://github.com/corpnewt/SSDTTime).
3. If your USB layout differs, rebuild the `USBMap.kext`.

## Credits

[OpenCore](https://github.com/acidanthera/OpenCorePkg), [Acidanthera](https://github.com/acidanthera), [ChefKiss (NootedRed)](https://github.com/ChefKissInc/NootedRed) and the AMD OSX community.
