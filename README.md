# Frida Launcher 🚀

**Effortlessly manage Frida server on Android devices and emulators with a single tap!**

<div align="center">
  <img width="331" alt="Frida Launcher Logo" src="logo.png" />
</div>

<div align="center">
  <a href="https://github.com/thecybersandeep/Frida-Launcher/stargazers"><img src="https://img.shields.io/github/stars/thecybersandeep/Frida-Launcher?style=social" alt="GitHub stars"></a>
  <a href="https://github.com/thecybersandeep/Frida-Launcher/network/members"><img src="https://img.shields.io/github/forks/thecybersandeep/Frida-Launcher?style=social" alt="GitHub forks"></a>
  <a href="https://github.com/thecybersandeep/Frida-Launcher/issues"><img src="https://img.shields.io/github/issues/thecybersandeep/Frida-Launcher" alt="GitHub issues"></a>
  <a href="https://github.com/thecybersandeep/Frida-Launcher/releases"><img src="https://img.shields.io/github/v/release/thecybersandeep/Frida-Launcher" alt="GitHub release"></a>
  <a href="https://github.com/thecybersandeep/Frida-Launcher/releases"><img src="https://img.shields.io/github/downloads/thecybersandeep/Frida-Launcher/total" alt="GitHub downloads"></a>
</div>

---

## 📋 Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [What's New in v2.0](#whats-new-in-v20)
- [Screenshots](#screenshots)
- [Demo](#demo)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Contributing](#contributing)
- [Acknowledgements](#acknowledgements)
- [Bonus Tip](#bonus-tip)

---

> **⚠️ Important:**  
> - **Root access** is mandatory on your device or emulator.  
> - A **Superuser Manager app** (e.g., Magisk, SuperSU) is required to grant root permissions.

---

## Introduction

Manually setting up Frida server is a chore—pushing binaries, tweaking permissions, and juggling terminal commands eats up your time. **Frida Launcher** changes the game!  

This lightweight Android app automates Frida server management with a clean, intuitive interface. Install, start, and monitor Frida with ease, so you can focus on what matters: **security research and pentesting**.  

Say goodbye to:
- Manual `adb push` and permission tweaks
- Architecture mismatches
- Terminal-based start/stop hassles  

**Frida Launcher** handles it all with **one-tap simplicity**. 🔧

---

## Features

- **Device Insights:** Detects your device architecture (e.g., `arm64`) and Frida status (installed/running).
- **Version Picker:** Choose from available Frida server versions in-app.
- **Custom Version Input:** Enter any Frida version number to install older versions (e.g., 16.7.19).
- **One-Tap Install:** Automatically downloads and sets up the right binary.
- **Easy Controls:** Start, stop, uninstall, or refresh with a single tap.
- **Reliable Stop:** Uses aggressive kill methods (`kill -9`) to ensure server stops reliably.
- **Live Logging:** View real-time Frida server logs with copy/clear options.
- **Custom Flags:** Run Frida server with custom arguments for advanced use cases.

---

## What's New in v2.0

- 🎨 **Completely Redesigned UI** with modern Material 3 design and vibrant cyan/purple color scheme.
- 📦 **Custom Version Input** - Now you can enter ANY Frida version number (e.g., 16.7.19) to install older versions that aren't in the dropdown list.
- 🛑 **Improved Server Stop** - Fixed the issue where Frida server sometimes wouldn't stop. Now uses `kill -9` with multiple fallback methods for reliable termination.
- ⚡ **Better Performance** with optimized code and smoother animations.
- 🔧 **Enhanced Error Handling** with clearer log messages.
- 📱 **Future-Proof** - Updated for Android 14/15 compatibility (2026 ready).

---

## Screenshots

---

### Main Dashboard

![dahbordremovebg-Photoroom](https://github.com/user-attachments/assets/2850b6fd-07ec-4f4e-bda3-9f7e7cb07fee)

---

### NFC Challenge (with Objection)

<img src="https://github.com/user-attachments/assets/de9e564e-f788-4eb3-bda5-54ae9dd0827c" alt="NFC Example" width="100%" />

---

### Logs Panel

![logsbgremove-Photoroom](https://github.com/user-attachments/assets/63d0815a-08ae-47bf-978a-892968aa791b)

---

## Demo

🎥 Demo video will be added soon! 

---

## Requirements

- **Android Version:** 7.0 Nougat (API 24) or higher
- **USB Debugging:** Enabled
- **Internet Connection:** Required for downloading Frida binaries
- **Root Access:** Mandatory
- **Superuser Manager App:** Installed (e.g., Magisk, SuperSU)

---

## Installation

### From Releases
Download the latest APK from the [Releases](https://github.com/thecybersandeep/Frida-Launcher/releases) page.

### Build from Source
```bash
git clone https://github.com/thecybersandeep/Frida-Launcher
cd Frida-Launcher

./gradlew clean assembleDebug

./gradlew installDebug
```

> 💡 **Pro Tip:** Open in Android Studio for a smoother build experience.

---

## Usage

1. Launch **Frida Launcher**.
2. Grant **Storage** and **Root (su)** permissions via your Superuser Manager app.
3. Tap **Refresh** to check Frida server status.
4. Select a Frida version from the dropdown, or select **"Custom Version..."** to enter any version number (e.g., 16.7.19 for older versions).
5. Tap **Install** to download and install.
6. Hit **Start** to run the server, or use **Custom** to start with custom flags.
7. Use **Stop** or **Uninstall** as needed.
8. Monitor real-time logs in the **Logs Panel**.

---

## How It Works

Frida Launcher streamlines Frida server management with smart automation. Here's the magic behind each action:

| Action | Description |
|:-------|:------------|
| **Refresh** | Scans device architecture (e.g., `arm64`), checks Frida installation/running status, and updates the UI. |
| **Install** | Downloads the correct Frida binary, places it in the right directory, and sets executable permissions (`chmod +x`). |
| **Start** | Runs the Frida server in the background using root (`su`). Logs confirm successful startup. |
| **Stop** | Kills the running Frida server process with root commands. |
| **Uninstall** | Removes the Frida server binary from the device. |
| **Logs Panel** | Streams live server logs with options to copy or clear. |
| **Custom Flags** | Allows passing custom arguments (e.g., `-D`, `-n`) to the Frida server. |
| **Help Dialogs** |  Flags info |

### Smart UI Logic
- Buttons (Start, Stop, Uninstall) activate only when relevant.
- **Install** unlocks after selecting a version.
- **Start** enables post-installation.
- **Stop** shows a helpful prompt if server isn't running.
- The UI **auto-refreshes** after actions like Stop or Uninstall to keep status accurate.

All actions are designed to prevent errors and ensure seamless server management.

---

## Contributing

Got ideas or fixes? We’d love your input!  
- Submit feedback or bug reports via [Issues](https://github.com/thecybersandeep/Frida-Launcher/issues).
- Fork, tweak, and send a [Pull Request](https://github.com/thecybersandeep/Frida-Launcher/pulls).  

Let’s make Frida Launcher even better! 🌟

---

*Happy Hacking!*

---

## Bonus Tip

If you find Frida Launcher useful, please consider giving it a ⭐ on GitHub!
