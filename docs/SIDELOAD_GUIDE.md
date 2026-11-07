# ApexShock: Android Sideloading & Installation Guide

This guide walks through installing and playing **ApexShock: Solaris Rift** on your Android mobile device or tablet.

---

## Direct APK Installation (Recommended for Phones & Tablets)

### Step 1: Download the Latest APK
Download the latest official package directly from [GitHub Releases](https://github.com/BiosSystem/ApexShock/releases/latest):
- Direct Download: [**`ApexShock-v0.3.0.apk`**](https://github.com/BiosSystem/ApexShock/releases/download/v0.3.0/ApexShock-v0.3.0.apk) (ARM64-v8a)

### Step 2: Allow Unknown Sources
Android requires permission to install apps outside the Google Play Store:
1. When prompted by your mobile browser (Chrome/Firefox/Samsung Internet), tap **Settings**.
2. Toggle on **Allow from this source** (or *Install unknown apps* under *Security & Privacy*).
3. Return to the download notification or tap the `.apk` file in your **Files / Downloads** app.

### Step 3: Install and Launch
1. Tap **Install** on the system package installer dialog.
2. Once installed, tap **Open** or launch **ApexShock** from your app drawer.
3. Enjoy 60 FPS mobile action in the Solaris Rift!

---

## Developer / ADB Sideloading (PC to Device)

If you have an Android device connected to your workstation via USB or Wireless ADB:

```bash
# Verify device connection
adb devices

# Install APK directly (replaces previous versions and preserves app data)
adb install -r ApexShock-v0.3.0.apk
```

---

## Desktop / Workstation Playtest

To play on Windows 10/11 using a mouse, keyboard, or USB controller:

1. Download [`ApexShock-v0.3.0-Bundle.zip`](https://github.com/BiosSystem/ApexShock/releases/download/v0.3.0/ApexShock-v0.3.0-Bundle.zip).
2. Extract the archive contents into any folder.
3. Launch with any Godot 4.3 binary:
   ```bash
   godot --main-pack ApexShock-v0.3.0.pck
   ```

### Default Workstation Controls:
- **Move**: `W`, `A`, `S`, `D` or Left Thumbstick
- **Aim & Shoot**: Mouse Direction / Left Click or Right Thumbstick
- **Active Gadget**: `[G]` or Right Bumper
- **Overdrive Surge**: `[H]` or Left Bumper
- **Armory / Menu**: `[TAB]` or `[M]`
