# Copyright 2025 Vivek Umrao

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

### Version 3.0.2 - Current
- ⏳ **Granular App Limits**: Introduced **Weekly** usage quotas. Parents can now set different time limits for each day of the week.
- 🛡️ **Biometric Authentication**: Integrated system-level biometric verification for sensitive administrative actions and password resets.
- 🎨 **Enhanced Limit Selection**: Redesigned the configuration UI with dedicated hour/minute pickers and a visual day selector.
- 🚀 **Infrastructure Optimization**: Enhanced device unlock processing and integrated background in-app update checks.

### Version 2.5.5
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
