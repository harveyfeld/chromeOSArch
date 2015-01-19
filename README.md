<h2>chromeOSArch</h2>
This interactive bash script will install Arch Linux ARM onto your SD card or USB drive from ChromeOS. This will allow you to boot directly onto the SD card and avoid ChromeOS or ChrUbuntu all together.

<h4>Installation guide for XE303C12</h4>
We need access to root for this script to work, we can get access by enabling developer mode.

The latest image of Arch Linux ARM seems to have broken drivers for wifi. Replace wget link on line 34 with http://rollback.archlinuxarm.org/os/{year}/{month}/{day}/ArchLinuxARM-chromebook-latest.tar.gz for older working versions of Arch.

<b>Enabling developer mode</b>

1. Turn off device.

2. Hold ESC and Refresh, then tap the power button.

3. Confirm switch to developer mode.

4. Press CTRL-D to boot when device restarts.

We cannot boot onto the our USB or SD card until we allow it via root.

<b>Enabling USB/SD booting</b>

1. After booting into ChromeOS in developer mode, tap CTRL-ALT-F2 to enter console.

2. Login using default user: <b>chronos</b>

3. Login to root using command: <b>sudo su</b>

4. Enter this command: <b>crossystem dev_boot_usb=1 dev_boot_signed_only=0</b>

5. Reboot device.

<b>Installing Arch</b>

Login as root in ChromeOS, then enter the following commands:
```
cd /tmp
curl -O https://raw.githubusercontent.com/NomCycle/chromeOSArch/master/chromeOSArch.sh
bash chromeOSArch.sh
```

After it finishes, reboot your device and tap CTRL-U to boot onto your USB or SD card when you are greeted with the bootloader.

Based on this guide: http://archlinuxarm.org/platforms/armv7/samsung/samsung-chromebook
