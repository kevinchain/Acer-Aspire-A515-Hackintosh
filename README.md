
  
  
  



![alt text](https://i.imgur.com/tNUJpOw.png  "Logo")
[click here to view full res image](https://i.imgur.com/zn9kw5U.png)
# 
 # Acer Aspire A515-51G i5-8250U/8GB/MX130
## <center>is what I picked instead of 12" MacBook</center>
### Hardware used:

![alt text](https://i.imgur.com/gh12k45.png  "specs")


### ⛔️ what is not working:

1. HDMI Audio

2. Wi-Fi card (You will need to replace it to the oe that's compatibile - DW1560 will do.)

  

### WARNING

Remove kexts + kext patches asociated with BCM94352Z(DW1560) if you do not have installed one

### Installation

  

There are many tutorials on how to install OSX on a PC class hardware. However using my Clover you can simply install OS 10.14 or newer on Acer Aspire A515. Make sure to connect USB keyboard and mouse as the I2C bus is supported (yet) during instalation.

  

### Post installation

Fix messed up audio on audio-layout 3 while using headphones
https://github.com/hackintosh-stuff/ComboJack

First things first, if you are using an SSD make sure to enable the TRIM support:

```

$ sudo trimforce enable

```

Install Clover on your hardware, copy EFI to EFI and run those commands:

```sh

$ sudo rm -rf /System/Library/Extensions/AppleACPIPS2Nub.kext

$ sudo rm -rf /System/Library/Extensions/ApplePS2Controller.kext

$ sudo rm -rf /System/Library/Extensions/ApplePS2SmartTouchPad.kext

$ sudo rm -rf /Library/Extensions/AppleACPIPS2Nub.kext

$ sudo rm -rf /Library/Extensions/ApplePS2Controller.kext

```

Then download VoodooPS2 from [here](https://bitbucket.org/RehabMan/os-x-voodoo-ps2-controller/downloads/) and run following commands:

```

$ cd directory-to-where-your-unzipped-download-is

$ sudo cp -R Release/VoodooPS2Controller.kext /Library/Extensions

```

Lastly, refresh the kernel cache by issuing following command:

```

$ sudo touch /System/Library/Extensions && sudo kextcache -u /

```

### reboot and enjoy!
### Credits:

[Clover EFI Bootloader](https://github.com/Clover-EFI-Bootloader/clover)

[Lilu.kext](https://github.com/acidanthera/Lilu/releases)

[VoodooPS2](https://github.com/RehabMan/OS-X-Voodoo-PS2-Controller)

[VoodooI2C](https://github.com/alexandred/VoodooI2C)

[Disable MX130](https://www.tonymacx86.com/threads/guide-disabling-discrete-graphics-in-dual-gpu-laptops.163772/)
