# SkillDash APK - Native Android Wrapper

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Platform: Android](https://img.shields.io/badge/Platform-Android%208.0%2B-green.svg)]()
[![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-blue.svg)]()

This repository contains the native Android APK wrapper for [SkillDash](https://skilldash.live), an **AI-powered platform** designed to bridge the skill gap for university and college students.

## 🎯 About SkillDash

SkillDash transforms career preparation into an engaging, gamified journey—helping you convert academic knowledge into real-world skills and connecting you directly to economic opportunities.

### ✨ Core Features

| Feature | Description |
|---------|-------------|
| 🔍 **AI Skill Quest** | Personalized AI-powered career analysis that asks strategic questions about your interests, aptitudes, and academic background to reveal hidden talents and suggest career paths tailored to the job market. |
| 💰 **Smart Coin System** | A balanced resource management system ensuring sustainable access to premium AI-powered career insights while maintaining affordability for all students. |
| 🎓 **Learn Skills** | Curated learning pathways and career courses tailored to your Skill Quest results and job market demands. Build job-ready skills employers actually need. |
| 📄 **AI Resume Feedback** | Instant, actionable resume feedback from our AI Coach tailored to job openings. Get detailed analysis of effectiveness, ATS optimization, and improvement suggestions. |
| 💼 **Career Opportunities** | Access to carefully curated part-time jobs, internships, and freelance opportunities specifically relevant to students. Build real-world experience while studying. |

## 📱 About This Build

SkillDash APK provides a **fullscreen native Android experience** using:
- **Capacitor** - Modern framework for wrapping web apps as native mobile apps
- **Next.js React** - Cutting-edge frontend framework
- **WebView** - Embedded browser optimized for seamless app experience

### Why Native App?

- ✅ **Native Feel** - Fullscreen display without browser chrome
- ✅ **No Close Button** - Feels like a true native app
- ✅ **Portrait Optimized** - Perfect layout for mobile devices
- ✅ **Offline Support** - Access cached content without connection
- ✅ **Home Screen** - Install directly to home screen like any Android app

## 🏗️ Architecture

```
skilldash-apk/
├── android/                         # Android native project (Capacitor)
│   ├── app/
│   │   ├── src/
│   │   │   ├── main/
│   │   │   │   ├── AndroidManifest.xml
│   │   │   │   ├── java/
│   │   │   │   └── res/              (App resources & layouts)
│   │   │   ├── test/                 (Unit tests)
│   │   │   └── androidTest/          (Instrumented tests)
│   │   └── build.gradle              (App build config)
│   ├── gradle/                       (Build tools)
│   ├── build.gradle                  (Root build config)
│   └── settings.gradle               (Project structure)
├── fdroid/                           # F-Droid configuration
│   ├── metadata.yml                  (App metadata)
│   └── build.yml                     (Build instructions)
├── capacitor.config.ts              # Capacitor configuration
├── build-apk.ps1                    # PowerShell build script
└── README.md                        # This file
```

## 📋 System Requirements

- **Android Version:** 8.0 (API 23) or higher
- **RAM:** 512 MB minimum
- **Storage:** ~50 MB for app installation
- **Internet:** Required for premium features (coins system)

## 🛠️ Technical Stack

- **Framework:** Capacitor 5.x
- **Frontend:** Next.js 14 with React & TypeScript
- **Styling:** Tailwind CSS
- **Build System:** Gradle 8.7.2
- **Target SDK:** Android 35 (latest)
- **Minimum SDK:** Android 23

## 🏗️ Build Configuration

### Build Information

- **Package Name:** `com.skilldash.live`
- **App ID:** `com.skilldash.live`
- **Version Code:** 1
- **Version Name:** 1.0.0
- **Compiled SDK:** 35
- **Target SDK:** 35
- **Minimum SDK:** 23

### Security Features

- ✅ Minification enabled for release builds
- ✅ ProGuard rules configured
- ✅ HTTPS enforced for server connections
- ✅ Internet permission only (no tracking permissions)

## 📦 Installation

### For Users

The SkillDash APK is available through:
- **F-Droid** (coming soon)
- [Official Website](https://skilldash.live)
- Direct APK downloads

### For Developers

To build the APK locally:

```bash
# Clone the repository
git clone https://github.com/zaifears/skilldash-apk.git
cd skilldash-apk/apk

# Install dependencies
pnpm install

# Build the Next.js web app
pnpm build

# Sync Capacitor (copy web assets to Android)
npx cap sync

# Build release APK
cd android
./gradlew clean assembleRelease

# Output APK location
android/app/build/outputs/apk/release/app-release.apk
```

### Prerequisites - Installation

Before building, ensure you have:

1. **Java Development Kit (JDK) 21 LTS**
   - Download from [Oracle JDK](https://www.oracle.com/java/technologies/downloads/#java21)
   - Or [Eclipse Adoptium](https://adoptium.net/)
   - Set `JAVA_HOME` environment variable
   - Verify: `java -version`

2. **Android SDK**
   - Download [Android Studio](https://developer.android.com/studio)
   - Or standalone [Android SDK Tools](https://developer.android.com/tools/releases/cmdline-tools)
   - Install SDK Platform 35 and Build Tools 34
   - Set `ANDROID_HOME` environment variable
   - Verify: `adb --version`

3. **Node.js 18+ and pnpm**
   - Download [Node.js LTS](https://nodejs.org/)
   - Install pnpm: `npm install -g pnpm`
   - Verify: `pnpm --version`

4. **Git**
   - Download [Git for Windows](https://git-scm.com/)
   - Configure: `git config --global user.name "Your Name"` and `git config --global user.email "your@email.com"`

See [SDK_AND_JDK_SETUP.md](SDK_AND_JDK_SETUP.md) for detailed setup guide.

## 🔨 Build Commands

### Complete Build Process (Windows PowerShell)

```powershell
# 1. Navigate to project
cd skilldash-apk/apk

# 2. Install Node dependencies
pnpm install

# 3. Build Next.js web app
pnpm build

# 4. Sync with Capacitor (copies web assets to Android)
npx cap sync

# 5. Build Android APK
cd android

# Debug APK
./gradlew assembleDebug

# Release APK (signed)
./gradlew clean assembleRelease
```

### Output Locations

```
# Debug APK
android/app/build/outputs/apk/debug/app-debug.apk

# Release APK (signed)
android/app/build/outputs/apk/release/app-release.apk
```

### Using Gradle Wrapper Directly

```powershell
# Navigate to android folder
cd android

# Debug build
cmd /c gradlew.bat assembleDebug

# Release build (signed)
cmd /c gradlew.bat clean assembleRelease
```

## 📋 Build Configuration Details

### APK Signing

The release APK is signed using a keystore file:

```
Keystore: skilldash.keystore
Algorithm: RSA 2048-bit
Validity: 10,000 days (~27 years)
Alias: skilldash
```

**Note:** The keystore file is NOT committed to git (added to `.gitignore` for security). Developers need their own keystore for local builds.

To create a keystore for local development:

```powershell
# Create a new keystore (valid for 10,000 days)
$keytoolPath = "C:\Program Files\Java\jdk-21\bin\keytool.exe"
& $keytoolPath -genkey -v -keystore "skilldash.keystore" `
  -keyalg RSA -keysize 2048 -validity 10000 `
  -alias skilldash `
  -storepass "your_password" `
  -keypass "your_password" `
  -dname "CN=Your Name,O=Your Organization,C=Your Country"
```

Update `android/app/build.gradle` with your keystore credentials.

### Build Types

**Debug Build:**
- Unsigned APK
- ~10-15 MB
- Useful for testing
- Fast build time

**Release Build:**
- Signed APK (~9.5 MB)
- Minified with R8
- Ready for distribution
- Longer build time (5-10 minutes)

## ✅ Latest Build Status

**Version 1.0.0 Release APK - Successfully Built**

```
Build Date: November 23, 2025
Build Type: Release (signed)
APK Size: 9.5 MB
Package: com.skilldash.live
Build Duration: ~2m 42s

Gradle Version: 8.10.2
Build Tools: 34.0.0
Android SDK Platform: 35
Java: JDK 21 LTS

Status: ✅ BUILD SUCCESSFUL
Location: android/app/build/outputs/apk/release/app-release.apk
```

### Build Process Summary

1. ✅ Pnpm dependencies installed
2. ✅ Next.js web app built (`pnpm build`)
3. ✅ Capacitor sync executed (`npx cap sync`)
   - Web assets copied to Android resources
   - Capacitor plugins configured
4. ✅ Gradle clean build initiated
   - Android SDK Platform 35 auto-installed
   - Android Build Tools 34 auto-installed
5. ✅ Java compilation completed
   - Capacitor Android library compiled
   - Capacitor Cordova plugins compiled
   - App source code compiled
6. ✅ R8 minification applied
   - Code optimized and obfuscated
   - APK size reduced
7. ✅ APK signed with release keystore
   - RSA 2048-bit signature applied
   - Package signed and aligned

## 📋 Configuration Files

### `capacitor.config.ts`
- App ID and name settings
- Web directory configuration
- Plugin settings (splash screen, HTTP)
- Server settings

### `android/app/build.gradle`

Gradle build configuration including:
- SDK versions (min: 23, target: 35, compile: 35)
- Version information
- Dependencies (AndroidX, Capacitor)
- Build types (debug, release)

### `android/app/src/main/AndroidManifest.xml`

Android app manifest with:
- App permissions (INTERNET only)
- Activity configuration
- Portrait orientation lock
- File provider setup

## 🧪 Testing

### On Physical Device

```bash
# Connect device with USB debugging enabled
adb install android/app/build/outputs/apk/debug/app-debug.apk
```

### On Emulator

1. Create and launch Android Emulator in Android Studio
2. Run the install command above

### Verification Checklist

- ✅ App launches fullscreen
- ✅ No close button visible
- ✅ Portrait orientation maintained
- ✅ Navigation works smoothly
- ✅ All features accessible

## 🌟 Key Features Deep Dive

### 🔍 AI Skill Quest

Strategic multi-question AI conversation analyzing your:
- Creative interests and aptitudes
- Academic strengths
- Practical skills comfort levels
- Work style preferences
- Career priorities

Results in comprehensive career recommendations tailored to job market realities.

### 💰 Coin System

Balanced approach to platform sustainability:
- Premium AI-powered analysis requires minimal coin investment
- Ensures high-quality, personalized career guidance
- Supports platform maintenance and AI model improvements
- Transparent resource requirements

### 📄 AI Resume Feedback

Strategic career advice including:
- Resume effectiveness analysis
- ATS system compatibility checks
- Keyword optimization for job searches
- Industry-specific formatting recommendations
- Local hiring practice insights

### 💼 Career Opportunities

Curated portal offering:
- Part-time positions aligned with academic schedules
- Internship opportunities for skill development
- Freelance projects for portfolio building
- Fair compensation and growth potential
- Real-world experience opportunities

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

## 🔗 Links

- **Website:** https://skilldash.live
- **GitHub (APK):** https://github.com/zaifears/skilldash-apk
- **Issues:** https://github.com/zaifears/skilldash-apk/issues
- **Discussions:** https://github.com/zaifears/skilldash-apk/discussions

## 📚 Documentation

Additional documentation available in this repository:

- [APK_BUILD_GUIDE.md](APK_BUILD_GUIDE.md) - Complete build instructions
- [SDK_AND_JDK_SETUP.md](SDK_AND_JDK_SETUP.md) - Environment setup
- [SETUP_CHECKLIST.md](SETUP_CHECKLIST.md) - Installation checklist
- [WHY_NO_CLOSE_BUTTON.md](WHY_NO_CLOSE_BUTTON.md) - Technical details

## 🎯 Mission

**Bridging the skills gap by making career development:**
- **Accessible** - Core features available with transparent resource requirements
- **Intelligent** - AI-powered insights tailored to job market realities
- **Practical** - Real-world job market insights and actionable guidance
- **Personalized** - Individual career recommendations based on unique strengths

## 🤝 Contributing

Contributions are welcome! Please feel free to:

- Report issues via [GitHub Issues](https://github.com/zaifears/skilldash-apk/issues)
- Submit pull requests with improvements
- Participate in [Discussions](https://github.com/zaifears/skilldash-apk/discussions)

## 📞 Support

For questions and support:

- 📧 Email: alshahoriar.hossain@gmail.com
- 🌐 Website: https://skilldash.live
- 💬 Discussions: [GitHub Discussions](https://github.com/zaifears/skilldash-apk/discussions)

---

<div align="center">
  <strong>🚀 Ready to discover your career potential?</strong><br/>
  <em>Join thousands of students building their future with SkillDash!</em><br/><br/>
  <a href="https://skilldash.live">Visit Website</a> • <a href="https://github.com/zaifears/skilldash-apk/issues">Report Issue</a> • <a href="https://github.com/zaifears/skilldash-apk/discussions">Discussions</a>
</div>

---

**Built with ❤️ for skill learners everywhere**
