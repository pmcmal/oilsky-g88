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
2. Open PowerShell or CMD and reboot the device into the bootloader:
   ```powershell
   adb reboot bootloader
