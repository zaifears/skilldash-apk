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
cd skilldash-apk

# Install dependencies
pnpm install

# Build for Android
./build-apk.ps1 debug

# Output APK location
android/app/build/outputs/apk/debug/app-debug.apk
```

### Prerequisites

- **Java Development Kit (JDK)** 17 or higher
- **Android SDK** (API 23+)
- **Node.js** 18+ and **pnpm**

See [SDK_AND_JDK_SETUP.md](SDK_AND_JDK_SETUP.md) for detailed setup guide.

## 🔨 Build Commands

### Quick Build (Windows PowerShell)

```powershell
# Debug APK
./build-apk.ps1 debug

# Release APK
./build-apk.ps1 release

# Clean build
./build-apk.ps1 clean

# Open Android Studio
./build-apk.ps1 open
```

### Manual Build

```bash
cd android
./gradlew assembleDebug      # Debug APK
./gradlew assembleRelease    # Release APK
```

## 📝 Configuration Files

### `capacitor.config.ts`

Main Capacitor configuration with:
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

- 📧 Email: contact@skilldash.live
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
