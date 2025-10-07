# Toshiba Portege Z30T-B (OpenCore EFI)

<img width="1920" height="1392" alt="macOS Toshiba Portege Z30TB" src="https://github.com/user-attachments/assets/4c0ec948-d5b6-4f20-b17b-3f67cfc845f1" />

This repository contains a fully working EFI configuration for **Toshiba Portege Z30T-B** with **Intel Core i7-5500U (Broadwell-U)** and **Intel HD 5500** graphics.  
The goal is to provide a stable and compatible OpenCore setup for macOS Monterey and Sonoma.

---

## 🧠 Hardware

| Component | Model / Version |
|------------|----------------|
| Laptop | Toshiba Portege Z30T-B |
| CPU | Intel Core i7-5500U (2C/4T, Broadwell-U) |
| GPU | Intel(R) HD Graphics 5500 (2 GB) |
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
- Power management
- USB ports (custom map under 15-port limit)
- SD card reader (Sinetek-rtsx)
- Trackpoint

---

## ❌ Not Working

- **Fingerprint reader** (Validity/Elan – not supported by macOS)
- Wake from fingerprint

---

### 🟢 macOS Sonoma confirmed working

<img width="1600" height="900" alt="Snímek obrazovky 2025-10-07 v 5 26 04" src="https://github.com/user-attachments/assets/e809003b-61d2-4ccc-8fe6-e3a53c2869c7" />

As of 2025, macOS **Sonoma 14.x** runs successfully on the **Toshiba Portege Z30-B (i7-5500U, Intel HD 5500)** using **OpenCore + OCLP 2.4.1**.

- Full graphics acceleration after OCLP **Post-Install Root Patch** (Broadwell GPU)  
- Wi-Fi works with `AirportItlwm.kext` (Sonoma 14.4 build)  
- SMBIOS: `MacBookPro12,1`  
- Upgrade from Monterey → Sonoma completed without issues  
- System stable and fully usable  
> Tested and confirmed functional configuration (EFI + OCLP).

### 🎧 Audio Jack & Scrolling Enhancements

If you need the **3.5 mm headphone jack** to work correctly (auto-switch between speakers and headphones),  
install **[ComboJack](https://github.com/hackintosh-stuff/ComboJack)** after macOS installation.  
ComboJack enables proper headset detection and microphone support on Realtek audio codecs.

For smoother and more natural **scrolling behavior**, you can also install  
**[Discrete Scroll](https://github.com/emreyolcu/discrete-scroll)** — a lightweight tool that improves touchpad and mouse scroll responsiveness on macOS.

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

- `SSDT-AC.aml` – general ACPI fixes (wake, power, sleep integration)
- `SSDT-EC-USBX.aml` – adds Embedded Controller device and USB power properties  
- `SSDT-GPRW.aml` – fixes sleep/wake methods (_GPRW)  
- `SSDT-HPET.aml` – IRQ conflicts fix for High Precision Event Timer  
- `SSDT-OC-XOSI.aml` – improves OSI compatibility for macOS  
- `SSDT-PNLF.aml` – enables display backlight control  
- `SSDT-PTSWAK.aml` – proper sleep/wake flow handling  
- `SSDT-SLPB.aml` – fixes sleep button behavior  

---

## 🧰 OpenCore Configuration

- **OpenCore Version:** 1.0.5 (Newest) 
- **SMBIOS:** `MacBookAir7,1`  
  _(generate your own serial numbers with `macserial`)_
- **boot-args:**

## 🧾 Project Status

| Status | Details |
|--------|----------|
| macOS Compatibility | ✅ Monterey (12.x), ⚙️ Working on Sonoma (14.x) |
| Stability | ✅ Daily-driver ready |
| Fingerprint Reader | ❌ Not supported |
| Audio Jack | ✅ With ComboJack |
| Scrolling | ✅ With Discrete Scroll |

## 📜 License

This EFI is provided for educational and experimental purposes only.  
Use at your own risk – the author is not responsible for any system damage or data loss.

#### 💰 Crypto Donations  

If you’d like to support my projects directly, you can donate via crypto:  
**BTC:** `bc1q9923r0f892lyd7sqf2j82xax03gpf58sntnwjs`  
**ETH:** `0x906cE31A56fb88ba202aed514CD7F36098e70A18`  
**SOL:** `BUFJ1oyx55taCvYSvVoE2xoYyHTgTSAAAKYTapJfJg53`

## 🙌 Credits

- [acidanthera](https://github.com/acidanthera) for OpenCore and kexts  
- [OpenIntelWireless](https://github.com/OpenIntelWireless) for Intel Wi-Fi/BT support  
- [Dortania Guide](https://dortania.github.io/OpenCore-Install-Guide/) for thorough documentation  
- [hackintosh-stuff/ComboJack](https://github.com/hackintosh-stuff/ComboJack) for audio jack support  
- Inspired by [yusufklncc/Toshiba-Portege-Z30-Hackintosh](https://github.com/yusufklncc/Toshiba-Portege-Z30-Hackintosh)
