# FaceGuardPro v4.0 Installation Guide

Welcome to FaceGuardPro v4.0! Elevate your home, office, and workplace security with our AI-powered smart security system.

---

## New Features (v4.0)

| Feature | Description |
|---------|-------------|
| **REST API Server** | External system integration via local API (FastAPI) |
| **NVR/IP Camera Support** | Professional camera systems via RTSP streams |
| **Multi-Camera View** | Monitor 4-16 cameras simultaneously |
| **System Resource Monitoring** | CPU, RAM, GPU usage tracking |
| **Event Broker** | Real-time event management system |
| **Advanced Camera Settings** | Per-camera mode and sensitivity settings |
| **User Feedback** | In-app feedback system |
| **Recognition Pool** | High performance through parallel recognition |

### Features from Previous Versions

| Feature | Description |
|---------|-------------|
| **Hybrid Recognition** | Face + Body + Skeleton combined recognition system |
| **6 Language Support** | Turkish, English, German, French, Spanish, Arabic |
| **Object Detection** | 15 different object categories (vehicles, animals, items) |
| **Baby Monitoring** | Zone-based motion detection and notifications |
| **Advanced Notifications** | Instant photo alerts via Telegram |
| **Multi-Device** | Use on up to 3 devices with a single account |

---

## Table of Contents

1. [Windows Installation](#windows-installation)
2. [Linux Installation](#linux-installation)
3. [macOS Installation](#macos-installation)
4. [REST API Usage](#rest-api-usage)
5. [NVR/IP Camera Setup](#nvrip-camera-setup)
6. [Features](#features)
7. [Troubleshooting](#troubleshooting)
8. [System Requirements](#system-requirements)

---

## Windows Installation

### Installation Steps

1. **Download the Setup File**
   - Download [`windows_faceguard_4.0_setup.exe`](https://github.com/eminaruk/FaceGuardPro/releases/download/v4.0/windows_faceguard_4.0_09.01.2026_setup.exe)

2. **Start the Installation**
   - Double-click the setup file
   - If you see a Windows SmartScreen warning:
     - Click "More info"
     - Click "Run anyway"

3. **Installation Wizard**
   - Select your language (English recommended)
   - Choose the installation location (default recommended)
   - Click "Next" buttons to complete installation
   - You can choose to create a desktop shortcut

4. **First Launch**
   - When installation is complete, check "Launch FaceGuardPro" and click "Finish"
   - OR launch from the desktop shortcut or Start Menu

### Upgrade (from v3.0 to v4.0)

If FaceGuardPro v3.0 or an earlier version is already installed:
- Run the setup file
- Answer "Yes" to "Do you want to update?"
- v4.0 new features will be listed for you
- Your existing settings and registered faces will be preserved

### Windows Defender SmartScreen Warning Solution

**Option 1: Allow Temporarily**
```
Click the "More info" link
Click "Run anyway" button
```

**Option 2: Add File to Safe List**
```
Right-click on the setup file
Select "Properties"
Check the "Unblock" checkbox at the bottom
Click "Apply" → "OK"
```

### Uninstall

**Via Control Panel**
```
Control Panel → Programs → Programs and Features
"FaceGuardPro" → Right-click → "Uninstall"
```

**Via Settings (Windows 10/11)**
```
Settings → Apps → Apps & features
"FaceGuardPro" → "Uninstall"
```

---

## Linux Installation

> **Note:** Linux v4.0 build will be released soon. You can currently use the v3.0 version.

### Installation Steps

1. **Download the ZIP File**
   - Download [`linux_faceguard_setup.zip`](https://github.com/eminaruk/FaceGuardPro/releases)

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

> **Note:** macOS v4.0 build will be released soon. You can currently use the v3.0 version.

### Installation Steps

1. **Download the ZIP File**
   - Download [`macos_faceguard_setup.zip`](https://github.com/eminaruk/FaceGuardPro/releases)

2. **Extract and Remove Quarantine**
   ```bash
   unzip FaceGuardPro_macOS.zip
   xattr -cr FaceGuardPro
   ```

3. **Launch the Application**
   - RIGHT-CLICK on FaceGuardPro → Select "Open"
   - Click "Open" again in the security warning

### "Unidentified Developer" Warning Solution

1. RIGHT-CLICK on the application (don't double-click)
2. Click on "Open"
3. Click "Open" in the security warning

### Camera Permission
```
System Preferences → Security & Privacy → Privacy → Camera
✓ Check FaceGuardPro
```

---

## REST API Usage

The REST API feature introduced in v4.0 allows you to integrate FaceGuardPro with external systems.

### Starting the API Server

1. From within the app: **Settings → API Management → Start API**
2. Default address: `http://localhost:8000`

### Example API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/v1/system/status` | GET | System status |
| `/api/v1/cameras` | GET | Camera list |
| `/api/v1/cameras/{id}/snapshot` | GET | Instant snapshot |
| `/api/v1/persons` | GET | Registered persons |
| `/api/v1/detection/status` | GET | Detection status |
| `/api/v1/logs` | GET | Event logs |
| `/api/v1/events/stream` | GET | SSE event stream |

### API Documentation

Automatic documentation when API is running:
- Swagger UI: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`

### Example Usage (Python)

```python
import requests

# System status
response = requests.get("http://localhost:8000/api/v1/system/status")
print(response.json())

# Registered persons
response = requests.get("http://localhost:8000/api/v1/persons")
for person in response.json():
    print(f"- {person['name']}")
```

### Example Usage (cURL)

```bash
# System status
curl http://localhost:8000/api/v1/system/status

# Camera list
curl http://localhost:8000/api/v1/cameras

# Instant snapshot
curl http://localhost:8000/api/v1/cameras/0/snapshot --output snapshot.jpg
```

---

## NVR/IP Camera Setup

With v4.0, you can connect your professional NVR and IP camera systems.

### Supported Protocols

| Protocol | Format | Example |
|----------|--------|---------|
| RTSP | `rtsp://user:pass@ip:port/path` | `rtsp://admin:123456@192.168.1.100:554/stream1` |
| HTTP | `http://ip:port/path` | `http://192.168.1.100:8080/video` |
| HTTPS | `https://ip:port/path` | `https://192.168.1.100/live` |

### Adding an NVR

1. **Settings → NVR Management → Add New NVR**
2. Enter NVR details:
   - Name: Name of the NVR system
   - IP Address: NVR's IP address
   - Port: Usually 554 (RTSP) or 8000
   - Username and password
3. Click **Scan Channels** button
4. Select the cameras you want

### Popular NVR Brand RTSP Formats

| Brand | RTSP URL Format |
|-------|-----------------|
| Hikvision | `rtsp://user:pass@ip:554/Streaming/Channels/101` |
| Dahua | `rtsp://user:pass@ip:554/cam/realmonitor?channel=1&subtype=0` |
| Uniview | `rtsp://user:pass@ip:554/media/video1` |
| Reolink | `rtsp://user:pass@ip:554/h264Preview_01_main` |

### Multi-Camera View

1. Click the **Multi-Camera** button on the main screen
2. Select grid layout: 2x2, 3x3, or 4x4
3. Assign a camera to each cell
4. Monitor all cameras in real-time

---

## Features

### Recognition Modes

| Mode | Description |
|------|-------------|
| **Face Recognition** | Real-time face detection and recognition |
| **Hybrid Recognition** | Face + Body + Skeleton combined recognition |
| **Body Recognition** | Recognition based on clothing and body features |
| **Skeleton Recognition** | Recognition based on body proportions |
| **Object Detection** | Detection of 15 different object categories |

### Security Modes

- **Security Mode:** Entry-exit tracking and notifications
- **Baby Monitoring Mode:** Zone-based motion detection
- **Object Detection Mode:** Vehicle, animal, item detection

### Supported Cameras

| Type | Format |
|------|--------|
| USB Webcam | Auto-detect |
| IP Camera | RTSP stream |
| NVR System | Multi-channel support |
| HTTP Stream | MJPEG |

### Telegram Notifications

1. Create a bot with [@BotFather](https://t.me/BotFather)
2. Get your Chat ID with [@userinfobot](https://t.me/userinfobot)
3. Enter the information in Settings → Telegram section

### Language Support

Turkish, English, Deutsch, Français, Español, العربية

---

## Troubleshooting

### Application won't open

- Temporarily disable antivirus software
- Re-download the files
- Restart your system

### Camera not found

- Make sure the camera isn't being used by another application
- Check camera permissions
- Try a different USB port for USB cameras

### IP Camera won't connect

- Check the RTSP URL format
- Verify username and password are correct
- Make sure the camera is on the same network
- Check that the firewall isn't blocking port 554

### API not working

- Make sure port 8000 isn't being used by another application
- Check firewall settings
- Verify API is active in Settings → API Management

### Firebase connection error

- Check your internet connection
- Check firewall settings
- Disable VPN if you're using one

### Windows: "VCRUNTIME140.dll not found"

Download Microsoft Visual C++ Redistributable:
https://aka.ms/vs/17/release/vc_redist.x64.exe

### macOS: "Damaged and can't be opened"

```bash
xattr -cr FaceGuardPro.app
```

### macOS: Apple Silicon (M1/M2/M3)

```bash
softwareupdate --install-rosetta
```

---

## System Requirements

### Windows

| Requirement | Minimum | Recommended |
|-------------|---------|-------------|
| Operating System | Windows 10 (64-bit) | Windows 11 |
| Processor | Intel Core i3 / AMD Ryzen 3 | Intel Core i5+ / AMD Ryzen 5+ |
| RAM | 4 GB | 8 GB |
| Disk Space | 2 GB | 4 GB |
| Internet | Required | - |

### Linux

| Requirement | Minimum | Recommended |
|-------------|---------|-------------|
| Operating System | Ubuntu 20.04+ | Ubuntu 22.04+ |
| Processor | Intel Core i3 / AMD Ryzen 3 | Intel Core i5+ / AMD Ryzen 5+ |
| RAM | 4 GB | 8 GB |
| Disk Space | 2 GB | 4 GB |

### macOS

| Requirement | Minimum | Recommended |
|-------------|---------|-------------|
| Operating System | macOS 11.0+ | macOS 13+ |
| Processor | Intel or Apple Silicon | Apple Silicon (M1/M2/M3) |
| RAM | 4 GB | 8 GB |
| Disk Space | 2 GB | 4 GB |

---

## Version History

| Version | Date | Key Features |
|---------|------|--------------|
| v4.0 | 2026-01-09 | REST API, NVR support, Multi-Camera |
| v3.0 | 2024-12-04 | Hybrid recognition, 6 language support |
| v2.0 | 2024-11-19 | Object detection, Baby monitoring |
| v1.0 | 2024-11-14 | Initial release |

---

## Support and Contact

- **X (Twitter):** [@eminarukk](https://x.com/eminarukk)
- **LinkedIn:** [eminaruk](https://www.linkedin.com/in/eminaruk/)
- **Email:** byemin00@gmail.com
- **Updates:** [GitHub Releases](https://github.com/eminaruk/FaceGuardPro/releases)

---

## License

This software is developed by Cingöz Systems. All rights reserved.

---

**Enjoy using FaceGuardPro!**

Last Updated: 2026-01-09 | Version: 4.0
