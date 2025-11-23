# SkillDash APK - Native Android Wrapper

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

This repository contains the native Android APK wrapper for [SkillDash](https://skilldash.live), a platform for discovering, learning, and mastering new skills.

## Overview

SkillDash APK provides a fullscreen native Android application experience using:
- **Capacitor** - Modern framework for wrapping web apps as native mobile apps
- **Next.js React** - Frontend framework for the SkillDash web application
- **WebView** - Embedded browser for displaying the app interface

## Key Features

✨ **Native App Feel**
- Fullscreen display without browser chrome
- No close button (feels like a native app)
- Portrait orientation locked

🚀 **Skill Learning Platform**
- Discover trending skills
- Track learning progress
- Access learning opportunities
- Offline support

📱 **Optimized for Mobile**
- Touch-friendly interface
- Responsive design
- Fast loading
- Minimal permissions required

## Architecture

```
skilldash-apk/
├── android/                    # Android native project (Capacitor)
│   ├── app/
│   │   ├── src/
│   │   │   ├── main/
│   │   │   │   ├── AndroidManifest.xml
│   │   │   │   ├── java/
│   │   │   │   ├── res/
│   │   │   │   └── assets/
│   │   │   ├── test/
│   │   │   └── androidTest/
│   │   └── build.gradle
│   ├── gradle/
│   ├── gradlew
│   ├── build.gradle
│   └── settings.gradle
├── fdroid/                     # F-Droid specific configuration
│   ├── metadata.yml
│   └── build.yml
├── capacitor.config.ts        # Capacitor configuration
├── build-apk.ps1              # PowerShell build script
└── README.md                  # This file
```

## Prerequisites

- **Java Development Kit (JDK)** 17 or higher
  ```powershell
  java -version
  ```
  
- **Android SDK**
  - Install via Android Studio or command-line tools
  - Set `ANDROID_HOME` environment variable
  
- **Node.js & pnpm**
  - Node.js 18+
  - pnpm 8+

## Building

### Quick Build (Windows PowerShell)

```powershell
# Debug APK
./build-apk.ps1 debug

# Release APK
./build-apk.ps1 release

# Clean build artifacts
./build-apk.ps1 clean

# Open Android Studio
./build-apk.ps1 open
```

### Manual Build

```bash
# Install dependencies
pnpm install

# Build web assets
pnpm build

# Sync with Android
pnpm cap-sync

# Build APK (debug)
cd android
./gradlew assembleDebug

# Output location
# android/app/build/outputs/apk/debug/app-debug.apk
```

## Configuration Files

### `capacitor.config.ts`
Main Capacitor configuration:
- App ID: `com.skilldash.app`
- App name: `SkillDash`
- Web directory: `android/app/src/main/assets/public/`
- Plugins: Splash screen, status bar, keyboard

### `android/app/src/main/AndroidManifest.xml`
Android app manifest with:
- App permissions (INTERNET)
- Activity configuration (portrait, fullscreen)
- File provider setup

### `android/app/build.gradle`
Gradle build configuration:
- Minimum SDK: API 23
- Target SDK: API 35
- Compile SDK: API 35

## Testing

### On Physical Device
```bash
# Connect device with USB debugging enabled
adb install android/app/build/outputs/apk/debug/app-debug.apk
```

### On Emulator
```bash
# Create and launch emulator in Android Studio
# Then run the install command above
```

## Version Information

Current version: **1.0.0**

Version structure:
- `versionCode`: Internal version number (integer)
- `versionName`: Public version string (semantic versioning)

To update versions, edit:
1. `android/app/build.gradle` - `versionCode` and `versionName`
2. `fdroid/metadata.yml` - Version information

## License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

## Support & Contributions

- 🐛 **Issues**: Report bugs on [GitHub Issues](https://github.com/zafears/skilldash-apk/issues)
- 🔧 **Contributing**: Pull requests welcome!
- 💬 **Discussions**: Start a discussion for questions

## Related Links

- **Live Website**: https://skilldash.live
- **Main Repository**: (Private - SkillDash web app)
- **F-Droid Page**: [Coming soon...]

## Notes

- The APK bundles web assets from the SkillDash website
- No close button for native app feel
- Portrait orientation locked for optimal mobile experience
- Internet permission required to fetch live content

---

**Built with ❤️ for skill learners everywhere**
