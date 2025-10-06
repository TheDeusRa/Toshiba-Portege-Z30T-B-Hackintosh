# Toshiba Portege Z30T-B Hackintosh (macOS OpenCore EFI)

This repository contains a fully working EFI configuration for **Toshiba Portege Z30T-B** with **Intel Core i7-5500U (Broadwell-U)** and **Intel HD5500** graphics.  
The goal is to provide a stable and compatible OpenCore setup for macOS Monterey.

---

## 🧠 Hardware

| Component | Model / Version |
|------------|----------------|
| Laptop | Toshiba Portege Z30T-B |
| CPU | Intel Core i7-5500U (2C/4T, Broadwell-U) |
| GPU | Intel HD5500 |
| RAM | 8–16 GB DDR3L |
| Storage | SATA / NVMe SSD (both supported) |
| Wi-Fi + Bluetooth | Intel (Itlwm + IntelBluetoothFirmware) |
| Audio | Realtek ALC2xx |
| Touchpad / Keyboard | PS2 (VoodooPS2Controller) |
| Display | 13.3" FHD Touchscreen (fully functional) |
| Fingerprint Reader | **Not supported** |

---

## ✅ Working Features

- Intel HD5500 with full acceleration (QE/CI, HDMI, external monitor)
- Audio via AppleALC (`layout-id=3`)
- Sleep / wake / battery reporting
- Touchpad & keyboard (VoodooPS2Controller)
- Wi-Fi + Bluetooth (IntelWireless drivers)
- Power management (SSDT-PLUG + XCPM)
- USB ports (custom map under 15-port limit)
- SD card reader (Sinetek-rtsx)
- Trackpoint

---

## ❌ Not Working

- **Fingerprint reader** (Validity/Elan – not supported by macOS)
- Intel RST (must be disabled in BIOS)
- Wake from fingerprint

---

## 🎧 Audio Jack Notice

If you want the **3.5 mm headphone jack** to work correctly (with automatic switching between speakers and headphones),  
you need to install **[ComboJack](https://github.com/hackintosh-stuff/ComboJack)** after macOS installation.  

ComboJack enables proper headset detection and mic functionality on Realtek codecs.

---

## ⚙️ Included Kexts

- [Lilu](https://github.com/acidanthera/Lilu)
- [WhateverGreen](https://github.com/acidanthera/WhateverGreen)
- [AppleALC](https://github.com/acidanthera/AppleALC)
- [VirtualSMC](https://github.com/acidanthera/VirtualSMC)
- [SMCBatteryManager](https://github.com/acidanthera/VirtualSMC)
- [VoodooPS2Controller](https://github.com/acidanthera/VoodooPS2)
- [IntelMausi](https://github.com/acidanthera/IntelMausi)
- [AirportItlwm](https://github.com/OpenIntelWireless/itlwm)
- [IntelBluetoothFirmware](https://github.com/OpenIntelWireless/IntelBluetoothFirmware)
- [BlueToolFixup](https://github.com/acidanthera/BrcmPatchRAM)
- [NVMeFix](https://github.com/acidanthera/NVMeFix)
- [Sinetek-rtsx](https://github.com/cholonam/Sinetek-rtsx)

---

## 🧩 ACPI Tables

- `SSDT-EC-USBX` – EC and USB power injection  
- `SSDT-GPRW` – fixes wake signal  
- `SSDT-PLUG` – proper CPU power management  
- `SSDT-PNLF` – backlight support  
- `SSDT-SLPB` – sleep button fix  
- `SSDT-OC-XOSI` – Windows ACPI compatibility  
- `SSDT-HPET` – IRQ fix  
- `SSDT-PTSWAK` – proper sleep/wake handling  

---

## 🧰 OpenCore Configuration

- **OpenCore Version:** 1.0.5  
- **SMBIOS:** `MacBookAir7,1`  
  _(generate your own serial numbers with `macserial`)_
- **boot-args:**

## 🧾 Project Status

| Status | Details |
|--------|----------|
| Functionality | ~99% (fingerprint unsupported) |
| Tested macOS | macOS 12 Monterey |
| OpenCore version | 1.0.5 |
| Last updated | October 2025 |

## 📜 License

This EFI is provided for educational and experimental purposes only.  
Use at your own risk – the author is not responsible for any system damage or data loss.

## 🙌 Credits

- [acidanthera](https://github.com/acidanthera) for OpenCore and kexts  
- [OpenIntelWireless](https://github.com/OpenIntelWireless) for Intel Wi-Fi/BT support  
- [Dortania Guide](https://dortania.github.io/OpenCore-Install-Guide/) for thorough documentation  
- [hackintosh-stuff/ComboJack](https://github.com/hackintosh-stuff/ComboJack) for audio jack support  
- Inspired by [yusufklncc/Toshiba-Portege-Z30-Hackintosh](https://github.com/yusufklncc/Toshiba-Portege-Z30-Hackintosh)
