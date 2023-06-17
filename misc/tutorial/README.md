# Welcome to Tips and Tutorial 
This section is aplicable for Redmi 10C/Redmi 10 (india)/Redmi 10 power these devices
They also know by their codename (fog/rain/wind)

## INFO
All three models are the same as they share the same processor, Snapdragon 680, built on a 6nm architecture. However, there are differences among the models:

- Region: The model "10C" is released in Indonesia but is not available in India.
- RAM: All three devices are available with different RAM options, ranging from 4GB to 8GB, along with varying storage capacities.
- Battery: The "10C" model has a 5000mAh battery, while the other models have a 6000mAh battery.

Required:
- Internet connectivity & Computer
- Installed platform-tools [click here for download](https://developer.android.com/tools/releases/platform-tools)
- unlocked bootloader [guide](https://xiaomiwiki.github.io/wiki/Unlock_the_bootloader.html)
- Appropriate [custom rom](https://t.me/Redmi10CUpdates) and [custom recovery](/misc/recovery/README.md)(unoffical / ported recovery as offical recovery is not available)

___

## Tips 
- Don't use any disable thermal modules
- Don't flash any weird or useless modules
- Confirm with admins of the devices group for correctness
- Taking logcat if you found bugs except OEMs rom and send to devs (read: [how taking logcat](https://gist.githubusercontent.com/Tanmsyffa/82e686caf6d7ea084505a5e85e02265e/raw/e52d7a5dd9120b284bd48e296c981651fe757a80/how_to_taking_logcat))

___

## Tutorial 

**1. Step flashing custom recovery**

1. Download the custom recovery file: Visit the official website or trusted sources for your preferred custom ROM and download the latest recovery file for your device. Ensure that you have the correct recovery file for your device model.

2. Connect your device to your computer: Use a USB cable to connect your device to your PC if it isn't already connected.

3. Enter fastboot mode: There are two methods to enter fastboot mode:
   - Method 1: Open a command prompt (Windows) or terminal (Linux/macOS) window on your computer and type the following command:
     ```
     adb reboot bootloader
     ```
   - Method 2: Power off your device. Then, hold the specific key combination (such as Volume Down + Power) to enter fastboot mode. Keep holding the buttons until you see the "FASTBOOT" or similar screen and then release.

4. Verify the connection: In the command prompt or terminal, type the following command to verify that your PC detects the device in fastboot mode:
   ```
   fastboot devices
   ```
   If you don't receive any output or encounter an error:
   - On Windows: Ensure that the device appears in the device manager without any warning symbols. Try different drivers until the `fastboot devices` command works.
   - On Linux or macOS: If you see a "no permissions" error, try running the `fastboot` command as root. If the output is empty, check your USB cable and port (preferably use a USB Type-A 2.0 cable or a USB hub).

5. Flash the custom recovery: In the command prompt or terminal, use the following command to flash the custom recovery (replace `<recovery_filename>` with the actual filename of the recovery you downloaded):
   ```
   fastboot flash recovery <recovery_filename>.img
   ```
   > Note: Some devices might require flashing to a specific slot (e.g., `boot_a` or `boot_b`). If the command fails, update fastboot to a newer release or specify the correct slot to flash to.
   > For more details on step 5 see next section

7. Reboot into recovery: Once the custom recovery is flashed, reboot your device into recovery mode to verify the installation:
   - Power off your device.
   - Hold the specific key combination (such as Volume Up + Power) to enter recovery mode. Keep holding the buttons until the recovery mode menu appears.

> Note:Ensure that you follow the official documentation or instructions specific to the custom ROM you are installing for any additional steps or requirements.

## step 5 with more details

1. Identify the available slots: Some devices use A/B partition slots, which means they have two sets of boot partitions: `boot_a` and `boot_b`. To identify the available slots on your device, you can use the command:
   ```
   fastboot getvar current-slot
   ```
   This command will display the currently active slot (e.g., `current-slot: a` or `current-slot: b`).

2. Determine the target slot: You need to determine the target slot where you want to flash the custom recovery. If your current slot is `a`, you may want to flash to `boot_b`, and vice versa. It's essential to ensure that the custom recovery is flashed to the inactive slot to avoid overwriting the active slot, which could cause booting issues.

3. Flash the recovery to the target slot: To flash the custom recovery to the desired slot, use the following command:
   ```
   fastboot flash boot_<target_slot> <recovery_filename>.img
   ```
   Replace `<target_slot>` with the appropriate slot identifier (`a` or `b`). For example, if you want to flash to `boot_b`, the command would be:
   ```
   fastboot flash boot_b <recovery_filename>.img
   ```

4. Reboot into recovery to verify: After flashing the custom recovery to the target slot, you can reboot your device into recovery mode to ensure the installation was successful. Follow the instructions specific to your device to enter recovery mode. For example, on some devices, you can hold Volume Up + Power to boot into recovery.

> Note: The steps mentioned above apply to devices that use A/B partition slots. If your device doesn't have A/B slots or follows a different partitioning scheme, you may not need to specify the slot while flashing the recovery. In such cases, the command would be:
```
fastboot flash recovery <recovery_filename>.img
```

It's important to consult the documentation or instructions provided by the custom ROM or your device manufacturer to ensure you're following the correct steps for flashing the custom recovery on your specific device.


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
