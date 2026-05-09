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

### Signing Configuration
```groovy
// Uses external secure.properties for credentials
signingConfigs {
    playstore {
        storeFile file('H:\\Key\\MyAppsKey.jks')
        // Password loaded from secure.properties
    }
}
```

### Build Types
- **Debug** - Development build with logging
- **Release** - Optimized with ProGuard obfuscation
- **Playstore** - Play Store distribution build
- **Update** - Update channel build

---

## 🔍 Testing

### Unit Tests
```bash
./gradlew test
```

### Instrumented Tests (Android Device/Emulator)
```bash
./gradlew connectedAndroidTest
```

### Build Verification
```bash
./gradlew build --scan
```

---

## 📋 Release Checklist

Before uploading to Google Play Console:

- [ ] Version code incremented
- [ ] Version name updated in `app/build.gradle`
- [ ] Build successful: `./gradlew packageAndCopyPlaystoreUpdate`
- [ ] AAB file generated and verified
- [ ] Debug symbols copied
- [ ] ProGuard mappings backed up
- [ ] App signed with correct keystore
- [ ] Tested on multiple device types
- [ ] Release notes prepared
- [ ] Screenshots/graphics updated
- [ ] Privacy policy URL verified
- [ ] Permissions justified

---

## 📱 Device Enrollment

### QR Code Enrollment

Child Safe supports QR code enrollment for easy device setup. This allows parents to quickly provision child devices with parental controls.

#### Enrollment Configuration

```json
{
  "android.app.extra.PROVISIONING_DEVICE_ADMIN_COMPONENT_NAME": "control.child.device/.admin.AdminReceiver",
  "android.app.extra.PROVISIONING_DEVICE_ADMIN_SIGNATURE_CHECKSUM": "eDjf9a0CXvneb7x0-Ev60EXUL5xXX48ZrPTAetQiyco",
  "android.app.extra.PROVISIONING_LEAVE_ALL_SYSTEM_APPS_ENABLED": true,
  "android.app.extra.PROVISIONING_MODE": "fully_managed_device",
  "android.app.extra.PROVISIONING_DEVICE_ADMIN_PACKAGE_DOWNLOAD_LOCATION": "https://github.com/vivek-umrao/ChildSafe/releases/download/latest/ChildSafe-playstore.apk"
}
```

#### QR Code

![QR Code for Enrollment](https://github.com/vivek-umrao/ChildSafe/releases/download/latest/qr_code.png)

#### Enrollment Steps

1. **Download the QR Code:**
   - Visit: [QR Code Download](https://github.com/vivek-umrao/ChildSafe/releases/download/latest/qr_code.png)

2. **Prepare the Child Device:**
   - Factory reset the device (recommended for clean setup)
   - Ensure the device is running Android 9.0+ (API 28)

3. **Scan the QR Code:**
   - During device setup, select the "QR Code" option
   - Scan the downloaded QR code
   - The device will automatically download and install Child Safe

4. **Complete Setup:**
   - Follow on-screen instructions
   - Configure parental controls
   - Set up monitoring features

#### Enrollment APK

Direct download link for manual installation:
- [Child Safe Enrollment APK](https://github.com/vivek-umrao/ChildSafe/releases/download/latest/ChildSafe-playstore.apk)

#### Requirements

- **Android Version:** 9.0+ (API 28)
- **Device Admin:** Enabled
- **Internet Connection:** Required for download
- **Storage:** Sufficient space for app installation

#### Troubleshooting

- **QR Code not scanning:** Ensure good lighting and camera focus
- **Download fails:** Check internet connection and try again
- **Installation blocked:** Enable "Unknown Sources" in device settings
- **Admin rights denied:** Ensure device supports device admin features

---

## 🔗 Resources

- [Google Play Console](https://play.google.com/console)
- [Android App Bundle Guide](https://developer.android.com/guide/app-bundle)
- [ProGuard & R8 Documentation](https://developer.android.com/studio/build/shrink-code)
- [Android Security Best Practices](https://developer.android.com/privacy-and-security)
- [Firebase Console](https://console.firebase.google.com)

---

## 📞 Support & Contact

For support, bug reports, or feature requests, please visit:
- **Google Play Store:** [Child Safe](https://play.google.com/store/apps/details?id=control.child.device)
- **Package ID:** `control.child.device`

---

## ✅ Recent Updates

### Version 2.5.5 (Code 51) - Current
- 🎨 **UX & Trust Rebranding**: Transformed the "Danger Zone" into **Advanced Management**. This eliminates user anxiety and prevents false malware perceptions.
- 📱 **User-Friendly Terminology**: Replaced technical jargon with intuitive terms. Used **End Device Management** (was Full Removal) and **Quick Sign Out** (was Session Only).
- 🛡️ **Cautionary Visual Design**: Introduced a balanced UI. It uses cautionary **Orange** accents for critical administrative actions instead of alarming red tones.
- 🧩 **Thematic Consistency**: Unified the management interface. It now uses the app's signature warm palette and professional iconography (Shield and Android icons).

### Version 2.5.4 (Code 50)
- 🔒 **Enhanced Kiosk Mode**: Moved kiosk lifecycle management to `AdminService`. This guarantees enforcement and automatic navigation when policy is enabled remotely.
- 🚀 **Remote Policy Enforcement**: Added real-time reactive navigation in `MainActivity`. The device enters or exits restricted environments immediately upon parent command.
- 🐛 **Data Integrity Fix**: Resolved `JsonSyntaxException`. Local data models now align with Firebase's nested structure for Call Logs, Contacts, and SMS.
- 🛠️ **Infrastructure Improvements**: Extracted Hilt EntryPoints for cleaner architecture. Implemented lazy dependency injection to support robust Direct Boot initialization.
- 📱 **UX Refinement**: Optimized application minimization logic using `moveTaskToBack`. This ensures seamless background operation.

### Version 2.5.3 (Code 49)
- 🏗️ **Architectural Overhaul**: Decoupled Firebase logic into specialized repository layers for better maintainability and testability.
- 💾 **Local-First Persistence**: Integrated Room-backed local storage to mirror all remote data, enabling offline access and faster UI responsiveness.
- ⚡ **Performance Optimization**: Implemented a memory-caching layer in Repositories to eliminate UI lag during data fetching.
- 🛡️ **Robustness**: Enhanced background service stability with improved support for device Direct Boot mode.

### Version 2.5.2 (Code 48)
- ✨ Enhanced UI with dark mode support
- 🐛 Bug fixes and performance improvements
- 📦 Migrated to Android App Bundle (AAB) for Play Store
- 🔧 Added automatic debug symbol collection

### Version History
See [Google Play Store Listing](https://play.google.com/store/apps/details?id=control.child.device) for complete version history.

---

## 📄 License

This project is proprietary. All rights reserved.

```
Copyright © 2025 Vivek Umrao
```

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

---

**Developed with ❤️ by Vivek Umrao**

*Last Updated: March 4, 2025*  
*Current Version: 2.5.5 (Code 51)*
*Target SDK: 37 | Min SDK: 28*
