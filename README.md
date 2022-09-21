# ubuntu-20.04-zephyrus-g14

Ubuntu 20.04 installation on ROG Zephyrus G14

## Create the USB Boot Drive

1. Download the Ubuntu 20.04 desktop image:  
   https://releases.ubuntu.com/20.04/ubuntu-20.04-desktop-amd64.iso  
   (This has built-in support for the WiFi chip in the G14.)

2. Write it to the USB drive with a tool like Rufus:  
   https://rufus.ie

## Prepare to Install from USB

1. Turn off drive encryption (BitLocker) in Windows.

2. Turn off fast startup in Windows.

3. Turn off secure boot in the BIOS menu.  
   (Hit ESC before the boot splash screen to enter the menu.)
   
## Boot from USB and Install
   
1. Boot from the USB drive.  
   (Hit ESC before the boot splash screen to enter the menu.)
   
2. Select "Try Ubuntu without installing" first.
   
3. Connect to a WiFi network.  
   (This lets the installer download updates and 3rd-party drivers.)

4. Install Ubuntu.  
   (Recommended: minimal installation alongside Windows, downloading updates, and installing 3rd-party drivers.)

## Switch to Liquorix Kernel

```
sudo add-apt-repository ppa:damentz/liquorix && sudo apt-get update
sudo apt-get install linux-image-liquorix-amd64 linux-headers-liquorix-amd64
sudo reboot
```

## Verify Functionality

1. Check that the correct Nvidia drivers are installed using the command:  
`nvidia-smi`

## Known Issues

- The wireless module might get stuck in a state where Bluetooth or WiFi (or both) doesn't work. To get it out of there, do the following:
  1. Power down the laptop.
  2. Unplug the charger.
  3. Power up and boot into Ubuntu.
  4. (optional) Plug back the charger.
