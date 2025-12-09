# FaceGuardPro v3.0 Installation Guide

Welcome to FaceGuardPro v3.0! Take your home, office, and workplace security to the next level with this AI-powered intelligent security system.

---

## New Features (v3.0)

| Feature                    | Description                                                              |
| -------------------------- | ------------------------------------------------------------------------ |
| **Hybrid Recognition**     | Combined Face + Body + Skeleton recognition system                       |
| **6 Language Support**     | Turkish, English, German, French, Spanish, Arabic                        |
| **Object Detection**       | Detection of 15 different object categories (vehicles, animals, objects) |
| **Baby Monitoring**        | Zone-based motion detection and alerts                                   |
| **Advanced Notifications** | Instant photo alerts via Telegram                                        |
| **Multi-Device Support**   | Use on up to 3 devices with a single account                             |

---

## Table of Contents

1. [Windows Installation](#windows-installation)
2. [Linux Installation](#linux-installation)
3. [macOS Installation](#macos-installation)
4. [Features](#features)
5. [Troubleshooting](#troubleshooting)
6. [System Requirements](#system-requirements)

---

## Windows Installation

### Installation Steps

1. **Download the Setup File**

   * Download [`windows_faceguard_3.0_setup.exe`](https://github.com/eminaruk/FaceGuardPro/releases/download/v3.0/windows_faceguard_3.0_4.12.2025_setup.exe)

2. **Start the Installation**

   * Double-click the setup file
   * If you see a Windows SmartScreen warning:

     * Click **“More info”**
     * Click **“Run anyway”**

3. **Installation Wizard**

   * Select your language (Turkish is recommended)
   * Choose the installation location (default is recommended)
   * Complete the installation by clicking **Next**
   * You can optionally create a desktop shortcut

4. **First Launch**

   * When installation is complete, check **“Launch FaceGuardPro”** and click **Finish**
   * Or start it from the desktop shortcut or Start Menu

### Updating (v2.0 to v3.0)

If FaceGuardPro v2.0 is already installed:

* Run the setup file
* Click **Yes** when asked “Do you want to update?”
* Your existing settings and saved faces will be preserved

### Windows Defender SmartScreen Warning Fix

**Option 1: Temporarily Allow**

```
Click “More info”
Click “Run anyway”
```

**Option 2: Add File to Trusted List**

```
Right-click the setup file
Select “Properties”
Check “Unblock” at the bottom
Click “Apply” → “OK”
```

### Uninstall

**Via Control Panel**

```
Control Panel → Programs → Programs and Features
Right-click “FaceGuardPro” → “Uninstall”
```

**Via Windows Settings (Windows 10/11)**

```
Settings → Apps → Apps & features
“FaceGuardPro” → “Uninstall”
```

---

## Linux Installation

> **Note:** Linux v3.0 build will be released soon.

### Installation Steps

1. **Download the ZIP File**

   * Download [`linux_faceguard_setup.zip`](https://github.com/eminaruk/FaceGuardPro/releases)

2. **Extract and Install**

```bash
unzip FaceGuardPro_Linux.zip
cd FaceGuardPro/
chmod +x install.sh
sudo ./install.sh
```

3. **Launch the Application**

```bash
/opt/FaceGuardPro/FaceGuardPro
```

Or from the application menu: Applications → FaceGuardPro

### Camera Permission

```bash
sudo usermod -a -G video $USER
# Log out and log back in
```

### Uninstall

```bash
sudo ./uninstall.sh
```

---

## macOS Installation

> **Note:** macOS v3.0 build will be released soon.

### Installation Steps

1. **Download the ZIP File**

   * Download [`macos_faceguard_setup.zip`](https://github.com/eminaruk/FaceGuardPro/releases)

2. **Extract and Remove Quarantine**

```bash
unzip FaceGuardPro_macOS.zip
xattr -cr FaceGuardPro
```

3. **Launch the Application**

   * Right-click the FaceGuardPro file → select **Open**
   * Click **Open** again on the security warning

### Fix for “Unidentified Developer” Warning

1. Right-click the application (do not double-click)
2. Click **Open**
3. Confirm by clicking **Open**

### Camera Permission

```
System Preferences → Security & Privacy → Privacy → Camera
✓ Enable FaceGuardPro
```

---

## Features

### Recognition Modes

| Mode                     | Description                                     |
| ------------------------ | ----------------------------------------------- |
| **Face Recognition**     | Real-time face detection and recognition        |
| **Hybrid Recognition**   | Combined Face + Body + Skeleton recognition     |
| **Body Recognition**     | Recognition based on clothing and body features |
| **Skeleton Recognition** | Recognition based on body proportions           |
| **Object Detection**     | Detection of 15 different object categories     |

### Security Modes

* **Security Mode:** Entry/exit tracking and notifications
* **Baby Monitoring Mode:** Zone-based motion detection
* **Object Detection Mode:** Detection of vehicles, animals, and objects

### Supported Cameras

| Type        | Format         |
| ----------- | -------------- |
| USB Webcam  | Auto-detection |
| IP Camera   | RTSP stream    |
| HTTP Stream | MJPEG          |

### Telegram Notifications

1. Create a bot with [@BotFather](https://t.me/BotFather)
2. Get your Chat ID via [@userinfobot](https://t.me/userinfobot)
3. Enter the details under Settings → Telegram

### Language Support

Turkish, English, Deutsch, Français, Español, العربية

---

## Troubleshooting

### Application does not open

* Temporarily disable your antivirus software
* Re-download the files
* Restart your system

### Camera not detected

* Make sure the camera is not being used by another application
* Check camera permissions
* Try a different USB port for USB cameras

### Firebase connection error

* Check your internet connection
* Review firewall settings
* Disable VPN if you are using one

### Windows: “VCRUNTIME140.dll not found”

Download Microsoft Visual C++ Redistributable:
[https://aka.ms/vs/17/release/vc_redist.x64.exe](https://aka.ms/vs/17/release/vc_redist.x64.exe)

### macOS: “Damaged and can't be opened”

```bash
xattr -cr FaceGuardPro.app
```

### macOS: Apple Silicon (M1/M2)

```bash
softwareupdate --install-rosetta
```

---

## System Requirements

### Windows

| Requirement      | Minimum             | Recommended    |
| ---------------- | ------------------- | -------------- |
| Operating System | Windows 10 (64-bit) | Windows 11     |
| Processor        | Intel Core i3       | Intel Core i5+ |
| RAM              | 4 GB                | 8 GB           |
| Disk Space       | 2 GB                | 4 GB           |
| Internet         | Required            | -              |

### Linux

| Requirement      | Minimum       | Recommended    |
| ---------------- | ------------- | -------------- |
| Operating System | Ubuntu 20.04+ | Ubuntu 22.04+  |
| Processor        | Intel Core i3 | Intel Core i5+ |
| RAM              | 4 GB          | 8 GB           |
| Disk Space       | 2 GB          | 4 GB           |

### macOS

| Requirement      | Minimum        | Recommended   |
| ---------------- | -------------- | ------------- |
| Operating System | macOS 10.15+   | macOS 12+     |
| Processor        | Intel or M1/M2 | Apple Silicon |
| RAM              | 4 GB           | 8 GB          |
| Disk Space       | 2 GB           | 4 GB          |

---

## Support & Contact

* **X (Twitter):** [https://x.com/eminarukk](https://x.com/eminarukk)
* **LinkedIn:** [https://www.linkedin.com/in/eminaruk/](https://www.linkedin.com/in/eminaruk/)
* **Email:** [byemin00@gmail.com](mailto:byemin00@gmail.com)
* **Updates:** [https://github.com/eminaruk/FaceGuardPro/releases](https://github.com/eminaruk/FaceGuardPro/releases)

---

## License

This software is developed by Cingöz Systems. All rights reserved.

---

**Enjoy using FaceGuardPro!**

Last Updated: 2024-12-04 | Version: 3.0
