Here is the updated README.md for your Telegram.monti.bio repository, tailored to reflect the advanced telephony, radio monitoring, and granular feature toggles shown in your screenshots.

```markdown
# Telegram.monti.bio - Custom Android Telegram Client

[Telegram](https://telegram.org) is a messaging app with a focus on speed and security. It’s superfast, simple and free.

This repository is a **customized fork** of the official [Telegram App for Android](https://play.google.com/store/apps/details?id=org.telegram.messenger) source code, specifically enhanced with deep telephony integration, modem configuration, and fine-grained user permissions/feature flags as demonstrated in the application data logs.

## 📸 Overview of Customizations
Based on the application's internal data files and event logs (viewable in the provided screenshots), this fork includes:
*   **Advanced Telephony & Radio Integration**: Full access and logging for Radio/Telecom interfaces, including `IMS_VOICE`, `IMS_VT`, `VOWIFI`, `DUN` (Dial-Up Networking), and dual-SIM support (PHONE=1). 
*   **Modem & System Configs**: Active interaction with `ModemConfigs`, `PhoneTypes`, `RsuConfigs`, and `Content_v5DB` for comprehensive device configuration.
*   **Granular Feature Toggles**: Extended control over internal application features via configuration flags (`allow_video_calls`, `allow_voice_calls`, `allow_emergency_buddy`).
*   **Permission Management**: Custom handling for `GET_CELL_INFO`, `ACCESS_NOTIFICATION_POLICY`, and strict event monitoring via `EventLog` and `TelecomCallLogs`.
*   **UI/UX Flags**: Controls for `use_video_autoplay`, `allow_chat_links`, `experimental_webview`, and `allow_download_files`.

## 🚀 Creating your Telegram Application
We welcome all developers to use our API and source code to create applications on our platform.
There are several things we require from **all developers** for the moment.

1. [**Obtain your own api_id**](https://core.telegram.org/api/obtaining_api_id) for your application.
2. Please **do not** use the name Telegram for your app — or make sure your users understand that it is unofficial.
3. Kindly **do not** use our standard logo (white paper plane in a blue circle) as your app's logo.
4. Please study our [**security guidelines**](https://core.telegram.org/mtproto/security_guidelines) and take good care of your users' data and privacy.
5. Please remember to publish **your** code too in order to comply with the licences.

## 📚 API, Protocol documentation
Telegram API manuals: https://core.telegram.org/api
MTproto protocol manuals: https://core.telegram.org/mtproto

## ⚙️ Compilation Guide (Specific to this Fork)
**Note**: This repository has been adapted to support reproducible builds with custom radio and system integration layers. 
Before publishing your own APKs, replace the dummy files and inject your own configurations.

### Requirements
*   Android Studio 3.4 or higher
*   Android NDK rev. 20
*   Android SDK 8.1

### Build Steps
1. **Clone the repository**:
   ```bash
   git clone https://github.com/montinode/Telegram.monti.bio.git
```

2. Configure Release Keys:
   · Copy your own release.keystore into TMessagesProj/config.
   · Fill out RELEASE_KEY_PASSWORD, RELEASE_KEY_ALIAS, and RELEASE_STORE_PASSWORD in gradle.properties.
3. Setup Firebase & Google Services:
   · Create two Android apps on the Firebase Console with application IDs org.telegram.messenger and org.telegram.messenger.beta.
   · Enable Firebase Cloud Messaging.
   · Download google-services.json and place it in the root folder of TMessagesProj.
4. Custom Feature Flags & Radio Configuration:
   · To modify the advanced radio and system flags (allow_video_calls, allow_emergency_buddy, maps_api_key, etc.), edit the internal data configuration files within the project (primarily located in TMessagesProj/src/main/java/org/telegram/messenger/BuildVars.java and additional JSON override files).
5. Compile & Run:
   · Open the project in Android Studio and build the app.
   · The Telephony and Config Logs will function as shown in the screenshots once running on an Android device with the necessary permissions (Radio & Device Config).

📋 License

This project is licensed under the same terms as the original Telegram source code. Please ensure you comply with the open-source licenses when distributing your build.

---

Forked from DrKLO/Telegram.

```
