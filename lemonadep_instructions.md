# Prerequisites:
- Device must be running OxygenOS version V14.0.0 H29,
- Flash the current build again using local install to ensure both slots have the same firmware. (Failing to do so will get you bricked)

# Clean flash:
- Reboot to bootloader
- Unzip recovery.zip
- Flash boot, vendor_boot, dtbo images
   -  `fastboot flash boot boot.img`
   -  `fastboot flash vendor_boot vendor_boot.img`
   -  `fastboot flash dtbo dtbo.img`
- Reboot to recovery
- Format data before sideload
- Sideload ROM zip
   -  `adb sideload voltage*.zip`
- Reboot and voila!

# Updating to a newer build (dirty flash):
- Sideload ROM zip
- Reboot and voila!

# If sideloading rom gives error 7:
- Reboot to recovery
- Enter fastbootd
- fastboot wipe-super super_empty.img
- Enter recovery
- Sideload the rom zip
- Format data
- Reboot

# If after sideloading rom, device boots to bootloader:
- Do clean flash steps again
- When it asks for Yes/No prompt for installing additional packages, select Yes
- After device reboots recovery, sideload again.
- This time when it asks for Yes/No prompt for installing additional packages, select No
- Format and Reboot