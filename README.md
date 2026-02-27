🛠️ Magisk Rooting Guide (Stock Firmware)
This guide provides a step-by-step walkthrough for rooting your device using Magisk on clean, stock software.

[!WARNING]
Unlocking the bootloader will wipe all user data. Ensure you have backed up your important files before proceeding.

1. System Preparation
Power on the device and complete the initial setup.

Enable Developer Options: * Navigate to Settings > Device Info.

Tap the Model (Oilsky G88) entry repeatedly (7 times) until a toast message appears: "You are now a developer!"

Configure Developer Settings:

Go to Settings > System > Developer Options.

Enable USB Debugging.

Enable OEM Unlocking.

2. Bootloader Unlocking
Connect your phone to your PC via USB.

Open PowerShell or CMD and reboot the device into the bootloader:

PowerShell
adb reboot bootloader
Once the phone is in Bootloader/Fastboot mode, execute the unlock command:

PowerShell
fastboot oem unlock
# OR (for newer devices):
fastboot flashing unlock
Note: Follow any on-screen prompts on your phone to confirm the unlock.

3. Initial Boot & Registration
After unlocking, reboot the system:

PowerShell
fastboot reboot
The system will perform a factory reset. Crucial: You must go through the setup process and enter the OS again to ensure the bootloader status is fully registered before proceeding with the patch.

4. Magisk Patching Process
Transfer the stock boot.img file from your clean firmware to the phone's internal storage.

Install the Magisk app.

In the app, tap Install > Select and Patch a File and select your boot.img.

Magisk will generate a file named magisk_patched.img (typically saved in the Download folder).

Copy this magisk_patched.img back to your computer.

Alternatively, you can use the pre-patched boot file available in the Google Drive link provided in this repository.

5. Flashing the Patched Boot Image
Reboot the phone into bootloader mode once more:

PowerShell
adb reboot bootloader
Flash the patched image to the boot partition:

PowerShell
fastboot flash boot magisk_patched.img
Finalize the process by rebooting:

PowerShell
fastboot reboot
Success! Your device is now rooted. Open the Magisk app to verify your status.
