# Copyright 2025 Vivek Umrao

# Child Safe - Parental Control App

<div style="text-align: center;">

![App Icon](app/src/main/ic_launcher-playstore.png)

**Take control of your child's activities**

[![Play Store](https://img.shields.io/badge/Google%20Play-Download-green?logo=google-play)](https://play.google.com/store/apps/details?id=control.child.device)
[![Android Version](https://img.shields.io/badge/Android-9.0%2B-brightgreen)](https://www.android.com/)
[![License](https://img.shields.io/badge/License-Proprietary-orange)](LICENSE)
[![Version](https://img.shields.io/badge/Version-2.5.5-blue)](app/build.gradle.kts)

</div>

---

## 📱 About Child Safe

**Child Safe** is a comprehensive parental control solution for parents. It helps monitor and manage children's digital activities. The app provides safe and secure oversight of device usage, app access, and online behavior. This ensures children's safety in the digital world.

### Key Features

✅ **Device Monitoring** - Real-time monitoring of child's device activities  
✅ **App Control** - Manage which apps children can install and use  
✅ **Usage Restrictions** - Set time limits and usage schedules  
✅ **Location Tracking** - Know where your child is at any time  
✅ **Secure Authentication** - Password and PIN protected access  
✅ **Kiosk Mode** - Secure, single-app or multi-app launcher environment  
✅ **User-Friendly Interface** - Easy navigation for parents  
✅ **Dark Mode Support** - Comfortable viewing in low-light conditions  
✅ **Device Management** - Administrative controls for secure device governance  

---

## 🛠️ Tech Stack

- **Language:** Java/Kotlin
- **Platform:** Android
- **Minimum SDK:** API 28 (Android 9.0)
- **Target SDK:** API 37 (Android 15)
- **Architecture:** Clean Architecture with Repository Pattern
- **Local Database:** Room Persistence Library
- **Backend:** Firebase (Provider-agnostic abstraction)
- **Version Code:** 51 (v2.5.5)

### Core Components
- **Repositories:** `AuthRepository` & `RemoteDataRepository` for data abstraction.
- **Persistence:** `PreferenceRepository` with Room-backed caching.
- **Dagger Hilt:** Dependency Injection for modularity.
- **Firebase:** Auth, Realtime Database, and Messaging.
- **Jetpack Components:** Navigation, Room, Lifecycle.

---

## 🚀 Getting Started

### Prerequisites

- **Android Studio** (latest version recommended)
- **JDK 17** or higher
- **Gradle 8.0+**
- **Android SDK 37**
- Google Play Services configured

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/vivek-umrao/ChildSafe.git
   cd ChildSafe
   ```

2. **Configure Firebase:**
   - Copy your `google-services.json` to the `app/` directory
   - Ensure Firebase is configured in your Firebase Console

3. **Build the project:**
   ```bash
   ./gradlew build
   ```

4. **Run on device or emulator:**
   ```bash
   ./gradlew installDebug
   ```

---

## 🔨 Building for Release

### Development Build
```bash
./gradlew assembleDebug
```

### Production Build (AAB)
```bash
./gradlew bundlePlaystore
```

### Complete Release Workflow
For a complete build with all variants (AAB, APKs, symbols, and mapping files):

```bash
./gradlew packageAndCopyPlaystoreUpdate
```

This generates:
- 📦 **Android App Bundle** (for Google Play)
- 📄 **Playstore APK** (for testing)
- 🐛 **Debug APK** (for local testing)
- 📤 **Update APK** (for update channel)
- 🔣 **Debug Symbols** (for crash reports)
- 📋 **ProGuard Mappings** (for de-obfuscation)

All files are copied to the directory specified in `build.gradle`.

---

## 📂 Project Structure

```
app/
├── src/
│   ├── main/
│   │   ├── java/control/child/          # Source code
│   │   ├── res/
│   │   │   ├── drawable/                # UI drawables and icons
│   │   │   ├── layout/                  # Activity layouts
│   │   │   ├── values/                  # Resources and strings
│   │   │   ├── menu/                    # Menu definitions
│   │   │   └── navigation/              # Navigation graphs
│   │   ├── AndroidManifest.xml          # App manifest
│   │   └── google-services.json         # Firebase config
│   ├── debug/                           # Debug-specific resources
│   ├── test/                            # Unit tests
│   └── androidTest/                     # Instrumented tests
├── build.gradle                         # App-level build configuration
└── proguard-rules.pro                   # ProGuard obfuscation rules
```

---

## 🔐 Security Features

- **End-to-End Encryption** - Secure communication between parent and child devices
- **Secure Authentication** - Password and PIN protection
- **Device Admin** - Administrative controls for device governance
- **ProGuard Obfuscation** - Code obfuscation for release builds
- **Debug Symbols** - Secure crash reporting without exposing source code

---

## 🎨 User Interface

### Parent Dashboard
- Device management
- Child activity monitoring
- App usage statistics
- Location tracking
- Time limit management

### Child Device Interface
- Simplified controls
- Restricted app access
- Activity logs
- Usage reports

---

## 🐛 Build & Deploy Guide

### Google Play Console Setup

1. **Create New Release:**
   ```
   Play Console → Your App → Release → Production → Create New Release
   ```

2. **Upload Android App Bundle (AAB):**
   - Use the AAB from the `playstore/` folder
   - Google Play will optimize APKs for each device

3. **Upload Debug Symbols:**
   - Upload files from the `symbols/` folder
   - Enables readable crash reports in Play Console

4. **Upload ProGuard Mappings:**
   - Upload `mapping/mapping.txt`
   - Allows de-obfuscation of crash stack traces

5. **Complete Release Information:**
   - Add release notes
   - Update screenshots if needed
   - Set rollout percentage
   - Review and publish

### Version Management

To release a new version:

```groovy
// In app/build.gradle
versionCode 51                    // Increment by 1
versionName "2.5.5"              // Update version string
```

Then rebuild:
```bash
./gradlew packageAndCopyPlaystoreUpdate
```

---

## 📊 Build Configuration

- **packageAndCopyPlaystoreUpdate**: Complete release build (AAB, APKs, symbols, mappings)
- **bundlePlaystore**: Build Android App Bundle (.aab file)
- **assembleDebug**: Build debug APK (Debug .apk file)
- **assemblePlaystore**: Build playstore APK (Playstore .apk file)
- **assembleUpdate**: Build update APK (Update .apk file)
- **copyPlaystoreDebugSymbols**: Copy native debug symbols (Symbol files)
- **copyPlaystoreMappingFiles**: Copy ProGuard mappings (mapping.txt)


---

## ⚙️ Gradle Configuration

# Parental Control - Child Safe 🛡️

**Parental Control - Child Safe** is a comprehensive Android solution designed to help parents protect their children's digital well-being. It provides real-time monitoring, remote device management, and smart safety features to ensure a balanced and secure mobile experience.

---

## ✨ Key Features

### 📱 Remote Monitoring & Safety
*   **Real-time Activity Tracking:** See exactly which apps are being used and for how long.
*   **Communication Audits:** Securely archive Call Logs, SMS, and Contacts to the parent dashboard for remote review.
*   **Location Snapshot & Trace:** Track current location in real-time or view a historical trace of movements.
*   **Action Status Reporting:** Get instant confirmation when remote commands (like locking or reboots) are executed.

### 🔒 Device Governance
*   **Instant Remote Lock:** Securely lock the child's device instantly from anywhere.
*   **Kiosk Mode:** Restrict the device to a single app or a specific set of safe apps, ideal for study time.
*   **Uninstall Protection:** Prevent the child from removing the safety app without your permission.
*   **App Hiding:** Keep administrative or distracting apps completely hidden.
*   **Remote Reboot:** Solve issues or enforce policy changes with a remote restart command.

### ⏳ Usage Management
*   **Smart App Limits:** Set daily time quotas for specific applications (e.g., 30 mins for games).
*   **Daily Allowed Time:** Define specific "allowed" hours for device usage.
*   **Policy Refresh:** Push new rules and restrictions instantly to all managed devices.

### 🛡️ Security & Anti-Tamper
*   **End-to-End Encryption:** Sensitive data (passwords, tokens) is protected with high-level encryption.
*   **Local Data Mirroring:** Uses Room-backed local storage to ensure logs are accessible even if the remote connection is intermittent.

---

## ⚙️ Device Enrollment (Advanced)

### QR Code Provisioning
Child Safe supports QR code enrollment for rapid device setup. This is the recommended method for fully managed device governance.

---

## 📝 Required Permissions

| Permission | Why we need it |
| :--- | :--- |
| **Location** | For real-time tracking and location history traces. |
| **SMS/Call Logs** | To archive communication history for parental review. |
| **Accessibility** | To enforce App Limits, Kiosk Mode, and prevent uninstalls. |
| **Device Admin** | For remote locking and advanced system security. |
| **Usage Stats** | To monitor and limit time spent in specific apps. |

---

## 🛠️ Tech Stack

*   **Language:** Java & Kotlin
*   **Architecture:** Clean Architecture with Repository Pattern.
*   **Backend:** Firebase Realtime Database & Auth.
*   **Persistence:** Room (Local Cache) & PreferenceRepository.
*   **DI:** Hilt / Dagger.
*   **Network:** OkHttp & REST for optimized metadata sync.

---

## 🚀 Getting Started

1.  **Firebase Setup:** Add `google-services.json` to the `app/` folder.
2.  **Authentication:** Enable Email/Password auth in your Firebase project.
3.  **Realtime Database:** Create a database and set appropriate rules.
4.  **Build:** Use Android Studio Ladybug+ to build the `:app` module.

---

## ✅ Recent Updates

### Version 3.0.2 (Code 52) - Current
- ⏳ **Granular App Limits**: Introduced **Weekly** usage quotas. Parents can now set different time limits for each day of the week.
- 🛡️ **Biometric Authentication**: Integrated system-level biometric verification for sensitive administrative actions and password resets.
- 🎨 **Enhanced Limit Selection**: Redesigned the configuration UI with dedicated hour/minute pickers and a visual day selector.
- 🚀 **Infrastructure Optimization**: Enhanced device unlock processing and integrated background in-app update checks.

### Version 2.5.5 - Current
*   🎨 **Advanced Management UI**: Rebranded the "Danger Zone" to **Advanced Management** for a more professional and less alarming experience.
*   🛡️ **Visual Safety Cues**: Introduced Orange accents for critical administrative actions.
*   🧩 **Thematic Consistency**: Unified iconography and color palettes across the Parent Dashboard.

### Version 2.5.4
*   🔒 **Enhanced Kiosk Mode**: Moved kiosk lifecycle management to a persistent background service.
*   🚀 **Real-time reactive navigation**: The device now enters/exits restricted modes immediately upon remote command.


## 📄 License & Copyright

**Copyright 2025 Vivek Umrao**

All rights reserved. Use of this software is subject to the terms of the license. Please ensure you comply with all local laws regarding parental monitoring.

---

**Developed with ❤️ by Vivek Umrao**
