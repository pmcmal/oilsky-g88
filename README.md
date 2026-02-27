# 🛠️ Magisk Rooting Guide (Stock Firmware)

This guide provides a step-by-step walkthrough for rooting your device using Magisk on clean, stock software.

> [!WARNING]
> **Unlocking the bootloader will wipe all user data.** Ensure you have backed up your important files before proceeding.

---

## 1. System Preparation
1. Power on the device and complete the initial setup.
2. **Enable Developer Options:** * Navigate to **Settings > Device Info**.
   * Tap the **Model (Oilsky G88)** entry repeatedly (7 times) until a toast message appears: *"You are now a developer!"*
3. **Configure Developer Settings:**
   * Go to **Settings > System > Developer Options**.
   * Enable **USB Debugging**.
   * Enable **OEM Unlocking**.

---

## 2. Bootloader Unlocking
1. Connect your phone to your PC via USB.
2. **Authorize Connection:** Check your phone screen for a prompt. Select **"Allow USB Debugging"** (check *"Always allow from this computer"* for convenience).
3. Open PowerShell or CMD and reboot the device into the bootloader:
   ```powershell
   adb reboot bootloader
4. Once the phone is in Bootloader/Fastboot mode, execute the unlock command:
   ```powershell
   fastboot oem unlock
  Note: Follow any on-screen prompts on your phone to confirm the unlock.
---

## 3. Initial Boot & Registration
1. After unlocking, reboot the system:
   ```powershell
   fastboot reboot
2. The system will perform a factory reset.
3. Now, every time you turn on the device, there will be an "Orange state" which is an alert that the device is unlocked, this cannot be avoided
4. Crucial: You must go through the setup process and enter the OS again to ensure the bootloader status is fully registered by the system before proceeding with the root.
   Note: The first start may take some time

---

## 4. Magisk Patching Process
1. Transfer the stock boot.img file from your clean firmware to the phone's internal storage.
2. Install the Magisk app. / may be on another device
3. In the app, tap Install > Select and Patch a File and select your boot.img.
4. Magisk will generate a file named magisk_xxxx.img (typically saved in the Download folder).
5. Change your name to magisk_patched, it'll be easier later
6. Copy this magisk_patched.img back to your computer.
  Note: Alternatively, you can use the pre-patched boot file provided in the Google Drive link in this repository. https://drive.google.com/file/d/1xSxhixdCyRRYNq9t36CPd77ul7RXDiwC/view?usp=sharing

---

## 5. Flashing the Patched Boot Image
1. in the folder where you have boot patched boot at the top of the bar, click and type cmd enter (to open command line terminal)
2. Reboot the phone into bootloader mode once more:
    ```powershell
   adb reboot bootloader
3. Flash the patched image to the boot partition:
   ```powershell
   fastboot flash boot magisk_patched.img
5. Finalize the process by rebooting:
    ```powershell
   fastboot reboot

---

## 4. Finishing installing magisk on your device
1. Turn on wifi and connect to the network on the oilsky device
2. The Magisk app should appear grayed out on your screen, click on it.
3. Magisk will download and install the full latest version apk
4. Open the Magisk app and you'll see install appear. Click install.
5. Magisk will reboot the device, installation will fail
6. Try installing Magisk again after it boots up. This time, you'll be presented with a menu to choose a method. Select "Direct install"
7. A terminal with logs will appear, everything should be ok and it will ask for a reboot at the end

# 🛠️ Clean firmware stock
https://drive.google.com/file/d/1xSxhixdCyRRYNq9t36CPd77ul7RXDiwC/view?usp=sharing

# 🛠️ Bonus: How to extract boot.img using Python (MTK Client)
If your device has newer software, I suggest taking a boot.img dump from the device or flashing the system from the link using a flash tool. https://drive.google.com/file/d/1xSxhixdCyRRYNq9t36CPd77ul7RXDiwC/view?usp=sharing
1. Requirements
Install Python: pip install mtkclient
Git clone the tool: git clone https://github.com/bkerler/mtkclient
Install drivers (Usbdk or LibUSB).
