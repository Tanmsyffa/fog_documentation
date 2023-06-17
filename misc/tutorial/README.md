# Welcome to Tips and Tutorial

Required:
- Internet connectivity
- Installed platform-tools [click here for download](https://developer.android.com/tools/releases/platform-tools)
- Appropriate [custom rom](https://t.me/Redmi10CUpdates) and [custom recovery](/misc/recovery/README.md)

___

## Tips 
- Don't use any disable thermal modules
- Don't flash any weird or useless modules
- Confirm with admins of the devices group for correctness
- Taking logcat if you found bugs except OEMs rom and send to devs (read: [how taking logcat](https://gist.githubusercontent.com/Tanmsyffa/82e686caf6d7ea084505a5e85e02265e/raw/e52d7a5dd9120b284bd48e296c981651fe757a80/how_to_taking_logcat))

___

## Tutorial 

**1. Step flashing custom recovery**
> make sure you have installed appropriate recovery image
- Reboot your phone to fastboot (vol - and power button)
- Open CMD and type:
  ```
  fastboot boot recovery.img
  ```
  Flashing succes but not reboot to recovery? Type `fastboot reboot recovery`.
- Your custom recovery has been flashed, enjoyy !

#

**2. Step flashing custom rom**
> make sure u have installed appropiate custom rom file
- Reboot to custom recovery (vol + and power button)
- Format data (wipe menu -> format data then swipe)
- Reboot recovery again 
- Flash the installed rom
- Flash ramdisk or recovery image (advanced -> ramdisk)
- Flash gapps and magisk (if vanilla rom and magisk if you want)
- Format data (optional)
- Reboot system
