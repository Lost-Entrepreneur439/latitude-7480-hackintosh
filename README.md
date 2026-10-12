macOS Monterey EFI for the Dell Latitude 7480 using OpenCore. I will try to keep this EFI up to date with the latest OpenCore and kexts

<img width="1280" height="1024" alt="image" src="https://github.com/user-attachments/assets/3a884e4d-7c08-45ed-a24c-025060b14f9a" />


# WARNING! SMBIOS DETAILS ARE NOT INCLUDED IN THE CONFIG.PLIST.
You will have to use [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) to generate an **MacBookPro13,1** SMBIOS for your system, and add them to the config.plist.

Make sure you're on BIOS 1.41.3 before continuing. You can get it from Dell's website. Older versions may cause issues.

## Other macOS versions?
No. Monterey is the latest supported by MacBookPro13,1, so it's all I'll ever support. If you want a different version, feel free to fork this repo to modify it for whatever version you want. Do note newer versions will likely require OCLP.

## System specs
Do note if your hardware differs, while unlikely, you may have issues.
- CPU: Intel Core i7-6600U
- GPU: Intel HD Graphics 520
- Audio: Realtek ALC256
- Wi-Fi: Intel 8265
- Ethernet: Intel I219-LM
- Disk: SK Hynix SC308 256GB

## Issues
- The touchpad lags, like it's being rapidly disconnected and reconnected. I believe this is a bug in AlpsHID. You're better off using a USB mouse or touchscreen.

If you notice any other problems, please open an issue (or pull request if you have a fix)

### BIOS settings
If you do not set these BIOS settings, macOS will **not** boot.

- General -> Boot Sequence -> Boot List Option -> UEFI
- General -> Advanced Boot Options -> Disable "Enable Legacy Option ROMs"
- System Configuration -> SATA Operation -> AHCI
- Security -> CPU XD Support -> Enable "Enable CPU XD Support"
- Seucre Boot -> Secure Boot Enable -> Disabled
- Intel® Software Guard Extensions™ -> Intel® SGX™ Enable -> Disabled
- Performance -> HyperThread control -> Enabled
- POST Behaviour -> Fastboot -> Thorough
- Virtualization Support -> Virtualization -> Enable "Enable Intel Virtualization Technology"
- Virtualization Support -> VT-D for Direct I/O -> Disable "Enable VT for Direct I/O"
