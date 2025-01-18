## Root Xiaomi TV Box S 2nd Gen - MDZ-28-AA
Instructions and Files to Root a Brand-New Xiaomi TV Box S 2nd Gen - MDZ-28-AA

![maxresdefault](https://github.com/user-attachments/assets/6eb5a8ba-3ce4-4565-b809-d74c8fbdabaa)

### Important: Do this on the first boot, DO NOT let the SYSTEM update itself or it may not work (but you can also test):

### Download the Necessary Files

1. Download the necessary files: [MDZ-28-AA.zip](https://www.mediafire.com/file/unpsu432truz652/MDZ-28-AA.zip/file)  ([mirror](https://11.to/MDZ-28-AA.zip)).
2. Extract `MDZ-28-AA`. It should contain the following files:

![necessary_files](https://github.com/user-attachments/assets/b3ceb176-90f5-4799-9955-17f93eceec1c)

### Install Fastboot Drivers

1. Install the fastboot drivers (if you don't have them yet):
   - Inside `MDZ-28-AA`, go to the folder `fastboot_driver`, right-click on `android_winusb.inf`, and choose `Install`.

![install_fastboot_driver](https://github.com/user-attachments/assets/5a326fbb-7d08-4e2c-b30b-383fc6e13f48)

### Bootloader Preparation

1. Unplug all wires except HDMI.
2. On the PC terminal, go to folder `MDZ-28-AA` and issue the following `fastboot` commands:

 - `fastboot reboot bootloader`

Terminal should say:

```bash
Rebooting into bootloader                            OKAY [  0.000s]
< waiting for any device >
```

3. Plug in the USB-A to USB-A cable.
4. Plug in the power.

Terminal should say:

```bash
Finished. Total time: 5.159s
```

5. Wait for bootloader screen, and then unlock:

 - `fastboot flashing unlock`

6. Confirm unlock:

 - `fastboot getvar unlocked`

```bash
unlocked: yes
Finished. Total time: 0.001s
```

### Flash all the necessary images:

 - `fastboot --disable-verity --disable-verification flash vbmeta_a vbmeta.img`

```bash
Rewriting vbmeta struct at offset: 0
Sending 'vbmeta_a' (2048 KB)                       OKAY [  0.097s]
Writing 'vbmeta_a'                                 OKAY [  0.026s]
Finished. Total time: 0.147s
```

 - `fastboot --disable-verity --disable-verification flash vbmeta_b vbmeta.img`

```bash
Rewriting vbmeta struct at offset: 0
Sending 'vbmeta_b' (2048 KB)                       OKAY [  0.096s]
Writing 'vbmeta_b'                                 OKAY [  0.027s]
Finished. Total time: 0.144s
```

 - `fastboot --disable-verity --disable-verification flash vbmeta_system_a vbmeta_system.img`

```bash
Sending 'vbmeta_system_a' (2048 KB)                OKAY [  0.097s]
Writing 'vbmeta_system_a'                          OKAY [  0.036s]
Finished. Total time: 0.153s
```

 - `fastboot --disable-verity --disable-verification flash vbmeta_system_b vbmeta_system.img`

```bash
Sending 'vbmeta_system_b' (2048 KB)                OKAY [  0.097s]
Writing 'vbmeta_system_b'                          OKAY [  0.026s]
Finished. Total time: 0.139s
```

 - `fastboot flash dtbo_a dtbo.img`

```bash
Sending 'dtbo_a' (2048 KB)                         OKAY [  0.097s]
Writing 'dtbo_a'                                   OKAY [  0.027s]
Finished. Total time: 0.140s
```

 - `fastboot flash dtbo_b dtbo.img`

```bash
Sending 'dtbo_b' (2048 KB)                         OKAY [  0.097s]
Writing 'dtbo_b'                                   OKAY [  0.027s]
Finished. Total time: 0.134s
```

 - `fastboot flash vendor_boot_a vendor_boot.img`

```bash
Sending 'vendor_boot_a' (24576 KB)                 OKAY [  1.167s]
Writing 'vendor_boot_a'                            OKAY [  0.297s]
Finished. Total time: 1.481s
```

 - `fastboot flash vendor_boot_b vendor_boot.img`

```bash
Sending 'vendor_boot_b' (24576 KB)                 OKAY [  1.157s]
Writing 'vendor_boot_b'                            OKAY [  0.596s]
Finished. Total time: 1.765s
```

 - `fastboot flash boot_a boot.img`

```bash
Sending 'boot_a' (65536 KB)                        OKAY [  3.092s]
Writing 'boot_a'                                   OKAY [  0.791s]
Finished. Total time: 4.089s
```

 - `fastboot flash boot_b boot.img`

```bash
Sending 'boot_b' (65536 KB)                        OKAY [  3.092s]
Writing 'boot_b'                                   OKAY [  0.787s]
Finished. Total time: 4.073s
```

 - `fastboot reboot fastboot`

```bash
Rebooting into fastboot                            OKAY [  0.000s]
< waiting for any device >
Finished. Total time: 15.159s
```

 - `fastboot flash super super-ab-737rw-sparse.img`

```bash
Sending sparse 'super' 1/7 (262128 KB)             OKAY [ 11.994s]
Writing 'super'                                    OKAY [  2.932s]
Sending sparse 'super' 2/7 (262096 KB)             OKAY [ 12.329s]
Writing 'super'                                    OKAY [  3.938s]
Sending sparse 'super' 3/7 (259588 KB)             OKAY [ 12.198s]
Writing 'super'                                    OKAY [  5.661s]
Sending sparse 'super' 4/7 (257016 KB)             OKAY [ 11.922s]
Writing 'super'                                    OKAY [  4.296s]
Sending sparse 'super' 5/7 (262140 KB)             OKAY [ 12.224s]
Writing 'super'                                    OKAY [  3.859s]
Sending sparse 'super' 6/7 (262120 KB)             OKAY [ 12.083s]
Writing 'super'                                    OKAY [  3.884s]
Sending sparse 'super' 7/7 (164402 KB)             OKAY [  7.630s]
Writing 'super'                                    OKAY [  3.918s]
Finished. Total time: 108.916s
```

 - `fastboot reboot`

```bash
Rebooting                                          OKAY [  0.000s]
Finished. Total time: 0.002s
```

### Configure the Device

1. Configure the device normally (Wi-Fi, Google account, etc.).
2. Enable developer options:
   - Click 5 times on: `Settings > System > About > Android TV OS Build`.

![android_tv_os_build](https://github.com/user-attachments/assets/292d7cfc-b804-40e5-b0d3-0dc4e1debc76)

3. Enable USB Debugging:
   - Navigate to: `Settings > System > Developer Options > USB Debugging`.

![usb_debugging](https://github.com/user-attachments/assets/71ce37d1-6eb2-44a1-89e9-fd401948271a)


### Install Magisk

From the PC, inside `MDZ-28-AA` folder, issue the following commands:

```bash
adb install Magisk-v28.1.apk
```

Open the Magisk app from within the apps menu:
- `Settings > System > Apps > See All Apps > Magisk > Open`

![magisk_open_app](https://github.com/user-attachments/assets/af1d3c87-d1a1-4be9-9d86-e43c221c4a40)


Or use:

```bash
adb shell am start -n com.topjohnwu.magisk/.ui.MainActivity
```

### Install the App & Patch

1. On Magisk Home activity, choose "`Install`" from the *App* Menu (You may need to give Magisk permission to install apps):

![magisk_install_app](https://github.com/user-attachments/assets/681d93b1-ad8d-4c7e-bae0-b254d5c275a7)

Install the app normally.

2. Go back to Magisk Home Activity, and choose "`Install`" from the *Magisk* Menu.

![magisk_install_patch](https://github.com/user-attachments/assets/46280b19-329a-4014-aa44-3e63b98b7454)

3. Select "`Direct Install (recommended)`".

![magisk_direct_install](https://github.com/user-attachments/assets/b75461e6-3936-4359-9c84-30154b196153)

4. Reboot the device using: `adb reboot` or use the remote control.

### Verify Root Access

If all goes well, the device should now have root access. Test this by issuing the following commands:

```bash
adb shell
jaws:/ $ su
```

Accept the Magisk prompt to give root access to the shell:

![magisk_root_auth](https://github.com/user-attachments/assets/f82fa546-70f6-4fe1-8027-f09a812a3456)

```bash
jaws:/ # whoami
root
```

----

Note:

 - If you are stuck on the Google TV logo, try going into fastboot as explained above and run: `fastboot -w`. This will erase all user data and should allow you to bypass the loop. Please note this will erase all your data, apps, etc.
 - Sources:
   - [Rooting Xiaomi TV Box S 2nd Gen (jaws) without UART/teardown](https://gist.github.com/supechicken/3c8378be3469bc2f82b7b319f202ed82)
   - [Обсуждение Xiaomi Discussion TV Box S 2nd Gen (MDZ-28-AA)](https://4pda.to/forum/index.php?showtopic=1068290)
 - You can change the Google TV Launcher with the Android TV: [https://github.com/davigamer987/atv-adfree-module](https://github.com/davigamer987/atv-adfree-module) - Flash as a Magisk Module
 - I'm not reponsible for any brick, be wise.
