# ThinkPad-L13-Yoga-Hackintosh

**Status: Success | Stable**

<img alt="L13 Yoga macOS" width="430" src="./Other/README_Resources/l13-yoga2.png" />

[![OpenCore](https://img.shields.io/badge/OpenCore-1.0.4-blue.svg)](https://github.com/acidanthera/OpenCorePkg) [![macOS-Unstable](https://img.shields.io/badge/macOS-14.7.5-brightgreen.svg)](https://www.apple.com/macos/) [![macOS-Unstable](https://img.shields.io/badge/macOS-15.4.1-orange.svg)](https://www.apple.com/ca/macos/)

**DISCLAIMER: ** As you embark on your Hackintosh journey you are encouraged to **READ** the entire README and [Dortania](https://dortania.github.io/getting-started/) guides before you start, or check out some [Youtube videos](https://www.youtube.com/c/TechNolli) to get an understanding of the install process. It will save many a message instructing you to read the manual. **I am not an expert**, I haven't forced you to do anything, so put on your big boy pants and take responsibility for any mess you get yourself into.

With that said I'm happy to help when/where I can. When you encounter bug or want to improve this repo, consider opening an issue or pull request. You can also find a wealth of knowledge on [Reddit](https://www.reddit.com/r/hackintosh/), [TonyMacX86](https://www.tonymacx86.com) or [Google](https://www.google.com).

## Introduction

<details> 
<summary><strong>This is not a guide!</strong></summary>

This is not a guide. It shoud only be used as a reference. I provide some tips and tricks I learned on my journey in building a hackintosh. The best way of using this is as a supplement to the OpenCore guide; if you have questions about how to setup your specific hardware, are unclear about what to do, or would like to see the settings I've used.

I understand that some may simply copy the EFI folder to their EFI partition. For clarity the EFI folder needs to go into the EFI partition.

```EFI
EFI (partition)
	EFI
	├── BOOT
	├── OC
```

It should work and your ThinkPad L13 Yoga should boot and work fine. **You will at minimum need to generate SMBIOS values if you want Apple services to work.** Note that all error reporting/logging has been turned off in the config.plist. You will have a difficult time trouble shooting with the setup provided. You can easily turn on the error reporting and logging if you follow the Dortania guide. Best of luck.

> **NOTE** if you simply wish to copy my EFI please do the following:
>
> 1. For a fresh install disable the WiFi and Bluetooth kexts, and set SecureBootModel to `Disabled` in the config.plist file.
> 
> 2. [Generate SMBIOS values](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake-plus.html#nvram) and add them in the config.plist (Use MacBookPro16,3)
>
> 3. Ensure the value of `showpicker` is  `true` in the config.plist file to provide the opencore menu when booting.
>
> 4. Prepare your install [USB](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/)
>
> 5. Move the entire EFI folder (with your modifications) to the proper partition on your [USB](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/mac-install.html#setting-up-opencore-s-efi-environment) (or [hard drive](https://dortania.github.io/OpenCore-Post-Install/universal/oc2hdd.html) once the install is complete).
>
> 6. [Install](https://dortania.github.io/OpenCore-Install-Guide/installation/installation-process.html#double-checking-your-work) - You'll need to select <kbd>F12</kbd> to get the boot menu options and **boot from the USB each time the computer restarts** until you've copied the EFI folder onto the hard drive. You may also need to select the correct boot option during install.


</details>  


<details> 
<summary><strong>This is a guide!</strong></summary>

To install macOS follow the guides provided by [Dortania](https://dortania.github.io/OpenCore-Install-Guide/) 🤔


</details>  


<details> 
<summary><strong>Shout out and credits</strong></summary>

**Shout out** to [oddish_enthusiast](https://www.reddit.com/user/oddish_enthusiast/) who pointed me in the right direction and let me know when OpenCore 0.6.7 fixed booting on 10^th^ gen processors. (He actually had it working before that).

**Shout out** to[DAlexis74](https://github.com/DAlexis74) for the DevicesProperties patches to enable HDMI.

**Shout out** to [alexjaixd](https://github.com/alexjaixd) for enabling Built-in SmartCard Reader #20

### Credit to all these great people whom I don't know but have made my hackintosh dreams come true:

- [EETagent](https://github.com/EETagent) for his repository (I like the layout of his guide and used it to create this one)

- The guys from [Acidanthera](https://github.com/acidanthera) that make this possible

- [Apple](http://apple.com) for macOS and HfsPlus.efi

- [corpnewt](https://github.com/corpnewt) for [USBMap](https://github.com/corpnewt/USBMap) and [CPUFriendDataProvider](https://github.com/corpnewt/CPUFriendFriend)

- [headkaze](https://github.com/headkaze) for [Hackintool](https://github.com/headkaze/Hackintool)

- [jwise](https://github.com/jwise) for [HoRNDIS](https://github.com/jwise/HoRNDIS)

- [Mieze](https://github.com/Mieze) for [IntelMausiEthernet](https://github.com/Mieze/IntelMausiEthernet)

- [OpenIntelWireless](https://github.com/OpenIntelWireless/IntelBluetoothFirmware/releases) for [IntelBluetoothFirmware](https://github.com/OpenIntelWireless/IntelBluetoothFirmware)

- [zhen-zen](https://github.com/zhen-zen) for [YogaSMC](https://github.com/zhen-zen/YogaSMC)

- Useful tools by [CorpNewt](https://github.com/corpnewt) and [headkaze](https://github.com/headkaze/Hackintool)

- And every other contributor

- People at [r/hackintosh](https://www.reddit.com/r/hackintosh/) for their advice and help


</details>


<details>
<summary><strong> Other Repositories </strong></summary>

- ThinkPad L13 Yoga -hackintosh repositories:

  - [hagenest/thinkpad-l13-yoga-hackintosh](https://github.com/hagenest/thinkpad-l13-yoga-hackintosh)

  - [Faridmau/hackintosh-Thinkpad-L13](https://github.com/faridmau/hackintosh-Thinkpad-L13)


</details>


<details>
<summary><strong>Hardware</strong></summary>

[![UEFI](https://img.shields.io/badge/UEFI-R15ET44W-lightgrey)](https://pcsupport.lenovo.com/ca/en/products/laptops-and-netbooks/thinkpad-l-series-laptops/thinkpad-l13-yoga-type-20r5-20r6/downloads/ds541927-bios-update-utility-bootable-cd-for-windows-10-64-bit-thinkpad-l13-l13-yoga)

### ThinkPad L13 Yoga

| Category  | Component                                            | Note                                                                                                                                       |
| --------- | ---------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Type      | 20R5, 20R6                                           |                                                                                                                                            |
| CPU       | Intel Core i5-10210U                                 |                                                                                                                                            |
| GPU       | Intel UHD 630                                        |                                                                                                                                            |
| SSD       | WD 512GB                                             | Replaced cursed PM 981 which still doesn't work reliably                                                                                   |
| Screen    | 13" FHD 1920x1080                                    | Multi touch and pen* support working                                                                                                       |
| Memory    | 8GB / 2666MHz DDR4                                   |                                                                                                                                            |
| Battery   | Integrated Li-Polymer 46Wh                           | Single battery                                                                                                                             |
| Camera    | 720p Camera and 5MP camera                           | Both cameras working                                                                                                                       |
| Wifi & BT | Intel Wireless-AC 9560                               | Use AirportItlwm for your macOS version and enjoy native Wi-Fi control.                                                                    |
| Input     | PS2 Keyboard & I2CHID TrackPad (touchscreen and pen) | I'm using [YogaSMC](https://github.com/zhen-zen/YogaSMC) for media keys. The kext is in the folder but **you'll need to install the app.** |


</details>


<details>
<summary><strong>Main software</strong></summary>

| Component    | Version |
| ------------ | ------- |
| macOS Sonoma | 14.7.5  |
| OpenCore     | v1.0.4  |


</details>


<details>
<summary><strong>ACPI Files</strong></summary>

| Component                   |
| --------------------------- |
| ssdt_data.aml               |
| SSDT-AWAC.aml               |
| SSDT-EC-USBX-LAPTOP.aml     |
| SSDT-Keyboard.aml           |
| SSDT-OCBAT1-lenovoPRO13.aml |
| SSDT-PNLF-CFL.aml           |
| SSDT-RHUB.aml               |
| SSDT-XOSI                   |


</details>


<details>
<summary><strong>Kernel extensions</strong></summary>

| Kext                    | Version |
| ----------------------- | ------- |
| AirportItlwm            | 2.3.0   |
| AppleALC                | 1.9.4   |
| BlueToolFixup.kext      | 2.6.9   |
| BrightnessKeys          | 1.0.3   |
| CPUFriend               | 1.2.9   |
| IntelBluetoothFirmware  | 2.4.0   |
| IntelBTPatcher          | 2.4.0   |
| IntelMausi              | 1.0.8   |
| itlwm                   | 2.3.0   |
| Lilu                    | 1.7.0   |
| NVMeFix                 | 1.1.2   |
| RealtekCardReader       | 0.9.7   |
| RealtekCardReaderFriend | 1.0.4   |
| SMCBatteryManager       | 1.3.5   |
| SMCProcessor            | 1.3.5   |
| SMCSuperIO              | 1.3.5   |
| USBMap                  | 1.0.1   |
| VirtualSMC              | 1.3.5   |
| VoodooI2C               | 2.9.1   |
| VoodooI2CHID            | 2.9.1   |
| VoodooPS2Controller     | 2.3.7   |
| WhateverGreen           | 1.6.9   |
| YogaSMC                 | 1.5.3   |

> The latest VoodooI2C release includes the fixes for pen and  touch support.


</details>


<details>
  <summary><strong>UEFI drivers</strong></summary>

| Driver              | Version           |
| ------------------- | ----------------- |
| HfsPlus.efi         | 1.0.0             |
| OpenRuntime.efi     | OpenCorePkg 1.0.4 |
| ResetNvramEntry.efi | OpenCorePkg 1.0.4 |


</details>


<details>
    <summary><strong>Screenshot</strong></summary>
    <br>
    <p float="left">
        <img src="./Other/README_Resources/ScreenShot1.png" alt="Monterey" width="427">
    </p>
</details> 

## Before installation


<details>  
<summary><strong>UEFI settings</strong></summary>

**Config**

- **Keyboard/Mouse**

  - `Trackpoint` **Enabled**

  - `Trackpad` **Enabled**

- **Display**

  - `Boot Display Device` **ThinkPad LCD**

  - `Total Graphics Memory` **512MB**

  - `Boot Time Extension` **Disabled**

- **CPU**

  - `Intel Hyper-Threading Technology` **Enabled**

**Security**

- `Password` **Disabled**

- `Security Chip` **Disabled**

- `Memory Protection -> Execution Prevention` **Enabled**

- `Virtualization -> Intel Virtualization Technology` **Enabled**

- `Virtualization -> Intel VT-d Feature` **Disabled**

- `Virtualization -> Enhanced Windows Biometric Security` **Disabled**

- `I/O Port Access -> FingerPrint Reader` **Disabled**

- `I/O Port Access -> Memory Card Slot` **Enabled**

- `Secure Boot -> Secure Boot` **Disabled**

- `Intel SGX -> Intel SGX Control` **Disabled**

- `Device Guard` **Disabled**

**Startup**

- `UEFI/Legacy Boot` **UEFI Only**

- `CSM Support` **No**

- `Boot Mode` **Diagnostics** (This can be changed to "Quick" once you know your system is running properly)


</details>


<details>
<summary><strong>Own prev-lang-kbd</strong></summary>

In the config.plist file you set the default language as outlined in the guide. You can either add it as a string or as a hex data using [ProperTree](https://github.com/corpnewt/ProperTree)

The setting is found in the config.plist under:

- NVRAM

  - 7C436110-AB2A-4BBB-A880-FE41995C9F82

Format is lang-COUNTRY:keyboard

- 🇺🇸 | [0] en_US - U.S --> en-US:0 --> (656e2d55 533a30 in HEX)

| Key           | Type   | Value   |
| ------------- | ------ | ------- |
| prev-lang:kbd | String | en-US:0 |

It is set to English but you can find alternatives here:

[AppleKeyboardLayouts](https://github.com/acidanthera/OpenCorePkg/blob/master/Utilities/AppleKeyboardLayouts/AppleKeyboardLayouts.txt)


</details>


<details>  
<summary><strong>MacOS Selection</strong></summary>

The EFI folder is setup for both Sonoma, and Sequoia. I used `MinKernel` and `MaxKernel` values in the config.plist to load the proper kexts based on which OS is being used. **It  works with Sequoia but there is still a WiFi issue:**

1. To use WiFi you need to install the Heliport app.

> I'm primarily using this EFI with Sonoma 14.7.5 at the moment.


</details>  

## Post-Install


<details>  
<summary><strong>TrackPad - Disable force touch</strong></summary>

If the **Battery** management **doesn't show up** in the System Preferences after the SSDT-OCBAT1-lenovoPRO13.aml file is added to your ACPI folder and config.plist file. You will not be able to change any trackpad settings. You may experience the annoying behaviour of clicking on the touchpad and it doing a **Force Touch** where the preview of the file is shown. I found this very annoying. You can disable force touch by modifying the file in `~/Library/Preferences/com.apple.AppleMultitouchTrackpad.plist`Opened it with Propertree and changed **ForceSuppressed** to **True**

Another trick to manage your trackpad, if you can't get the battery to work, is to connect a bluetooth trackpad. Once the bluetooth trackpad is connected you can adjust the settings. Disconnect the bluetooth trackpad and your built in one will maintain those settings.

I used these methods prior to adding the SSDT-OCBAT1-lenovoPRO13.aml from [hagenest/thinkpad-l13-yoga-hackintosh](https://github.com/hagenest/thinkpad-l13-yoga-hackintosh) repo.


</details>  


<details>  
<summary><strong>Generate your own SMBIOS</strong></summary>

Use [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) to create your own serial #... based off of your preferred model.

- MacBookPro16,3 -`What I used`

**Note:** If you use a different SMBIOS model than the MacbookPro16,3 that I've used. The provided USB mapping will not work.  You will need to edit the **USBMap.kext file**.  You can right click on the file and select **Show Package Contents**.  From there you can open the Info.plist file in ProperTree and change MacBookPro16,3 to whatever Model ID you've chosen. This should provide a working USBMap.kext.


</details>


<details>  
<summary><strong>CPUFriend power management</strong></summary>

Generate `CPUFriendDataProvider` or `ssdt_data.aml` (choose one) for your machine [here](https://github.com/acidanthera/CPUFriend) or use the ssd_data.aml file provided. My files are set for power conservation over performance. Highly recommended that you use power management.


</details>


<details>
<summary><strong>USB Port Mapping</strong></summary>

While first port mapping I followed the [Dortania guide here](https://dortania.github.io/OpenCore-Post-Install/usb/#macos-and-the-15-port-limit) with USBInjectAll.kext install...  when doing so the internal USB ports did not show up and the cameras, touch screen, and bluetooth did not function. I noticed on the `USBmap tool` screen that RHUB was showing so I Googled it and it brought me back to the [Dortania guide here](https://dortania.github.io/OpenCore-Post-Install/usb/manual/manual.html#special-notes). I added the SSDT-RHUB.aml to the APCI folder rebooted and all the ports showed up. I then mapped the USB ports creating the included USBMap.kext file.


</details>


<details> 
<summary><strong>Audio Setup</strong></summary>

The L13 Yoga has CX8070 for audio which requires the boot-arg **or** device property below. You can use the boot-args to initially setup your config.plist file as suggested in the guide or simply add the device property. Everything should work, built-in microphone, speakers, headphone jack and microphone.

NVRAM:

| Key       | Value    |
| --------- | -------- |
| boot-args | alcid=15 |

DeviceProperties

| Key                        | Type       | Value        |
| -------------------------- | ---------- | ------------ |
| PciRoot(0x0)/Pci(0x1F,0x3) | Dictionary |              |
| layout-id                  | Data       | **0f000000** |


</details>

## Updating or Installing MacOS


<details>
<summary><strong>Install or update tips</strong></summary>

When updating MacOS the following is recommended:

1. Disable all WiFi and Bluetooth kexts in the **config.plist** file.

2. Set SecureBootModel to `Disabled` in the **config.plist** file.

> Once your OS is updated you can re-enable the above settings.
>
> Alternatively you can install follow [these instructions](https://www.reddit.com/r/hackintosh/comments/193wqha/having_issues_with_ota_updates_read_here/) to install and use RestrictEvents.kext.


</details>

<details>
<summary><strong>Stuck on "Less than a minute remaining..." (OFFLINE INSTALL)</strong></summary>

Usually when installing (in my particular case, MacOS Sequoia 15.5), it might get stuck at "Less than a minute remaining..."

This is completely normal, and would be expected as the system is performing some heavy cryptography.

Try pressing the Caps Lock key, if the light turns on, the system isn't fully frozen, just busy.

> https://dortania.github.io/OpenCore-Legacy-Patcher/TROUBLESHOOTING.html#stuck-on-less-than-a-minute-remaining
> See the above link to see the source for this information.

</details>

<details>
<summary><strong>Infinite boot loop on the install process (OFFLINE INSTALL)</strong></summary>

I've experienced some issues when installing MacOS Sequoia 15.5 with OpenCore, where the install completely finishes the first stage,
but then restarts to the second install screen. At this point, you might get through the ~30 minutes remaining counter,
but once at the end, it restarts to return at the ~30 minutes remaining counter.

I mitigated this issue by simply formatting the EFI partition to MS-DOS FAT within the MacOS Disk Utility from a VM,
and then mounting it on my Windows PC, as creating the EFI partition on MacOS, (for me at least), left unnessecary files
in the EFI folder.

</details>

## Status


<details>
<summary><strong>What's working ✅</strong></summary>

- [x] Battery percentage

- [x] Bluetooth - Intel Wireless-AC 9560

- [x] Wifi - Intel Wireless-AC 9560

- [x] CPU power management

- [x] GPU UHD hardware acceleration / performance

- [x] iMessage, FaceTime, App Store, iTunes Store. `Generate your own SMBIOS`

- [x] Intel I219-V Ethernet port -`works with the Lenovo dongle`

- [x] Keyboard `Volume and brightness hotkeys, with YogaSMC and BrightnessKey kexts`

- [x] Audio - Conexant CX8070 -`"alcid=15" - or see setup above`

- [x] Microphone

- [x] Sleep/Wake

- [x] TrackPoint  `Works perfectly. Just like on Windows or Linux.`

- [x] USB Ports `USB map created.`

- [x] Web camera `Both cameras are working after the USB mapping was done.`

- [x] TouchPad `1-3 fingers swipe gestures`

- [x] Multi-Touch Screen `Pen also working`

- [x] Graphical Boot menu `OpenCanopy (It does work. Not included in OC folder as I generally skip the boot menu.)`

- [x] HDMI

- [x] SD Card reader

- [x] SmartCard Reader `not available on all units`


</details>


<details>  
<summary><strong>What's not working ⚠️</strong></summary>

- [ ] Fingerprint reader - `No. Don't expect macOS driver any time soon.`

- [ ] Samsung PM 981 NVME drive - `Still unstable. Could work for some, not for others.`

- [ ] Intel Optane - `It causes Kernel Panic in boot` (see [issue #14](https://github.com/seven-of-eleven/Lenovo-ThinkPad-L13-Yoga-Hackintosh/issues/14))


</details>


<details> 
<summary><strong>Untested</strong></summary>

- [ ] Boot chime `should work I just haven't tried it`

- [ ] FileVault `should work I just haven't tried it`

- [ ] Sidecar wired

- [ ] Sidecar wireless

- [ ] Windows/Linux from OC boot menu`I'm not dual booting my system but there's no reason it shouldn't work.`


</details>
