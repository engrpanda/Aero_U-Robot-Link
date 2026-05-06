# Privacy Policy — Aero (U-Robot Link)

**Effective Date:** 6 May 2026  
**Last Updated:** 6 May 2026  
**Application name:** Aero — U-Robot Link  
**Application package ID:** `com.Aero.engrpanda`  
**Developer:** Engr. J R Cabataña, ECT  
**Contact:** engrpandaece@gmail.com 
**Repository:** https://github.com/engrpanda/Aero_U-Robot-Link

---

## 1. Plain-language summary

**Aero does not collect, sell, or share any personal data.** It is a controller app that runs entirely on your phone and talks directly to robots and microcontrollers you own (Arduino, ESP8266, ESP32, ESP32-CAM, OrionStar, LEGO MINDSTORMS NXT, LEGO MINDSTORMS EV3). Nothing you do inside Aero is uploaded to any server operated by the developer.

If you only read one section of this policy, this is the one that matters:

- No analytics, no advertising SDKs, no crash-reporting services, no user accounts.
- No data leaves your phone except the commands you intentionally send to your own robot over Bluetooth, BLE, or WiFi.
- The only optional cloud-touching feature is **Voice Control**, which uses Android's built-in speech recognition. That feature is off until you turn it on.

The rest of this document explains in detail what Aero does and does not do, what permissions it requests, and why.

---

## 2. Information we do not collect

Aero does **not** collect, store, transmit, or process any of the following:

- Your name, email address, phone number, or any account credentials.
- Your device's IMEI, advertising ID, or any other persistent identifier intended for tracking.
- Your contacts, calendar, SMS, call logs, photos, or files.
- Your precise GPS location.
- Browsing history, app usage history, or behavioural analytics.
- Voice recordings or transcripts (see Section 4 for clarification on Voice Control).
- Sensor readings from any robots you connect.
- Crash logs, telemetry, or diagnostics (the app does not include any third-party crash-reporting SDK).

We do not maintain a backend service. There is no "Aero account" to sign up for. There is no way for the developer to see what you do inside the app.

---

## 3. Information stored locally on your device

Aero saves the following information **only on your phone** using Android's standard `SharedPreferences` and local file storage. None of this is transmitted anywhere by Aero:

- Your custom button layouts (labels, commands, colours, grid positions).
- Your saved profiles and named layouts.
- The address (Bluetooth MAC, IP) of the last device you successfully connected to, so the app can auto-reconnect.
- Your LEGO brick configuration (drive port assignments, max power, deadband, etc.).
- App preferences such as light/dark mode and which panels are visible.
- The contents of the in-app Terminal log for the current session.
- Last-known sensor values displayed on the IoT Dashboard (in-memory only by default).

This data is wiped when you uninstall Aero or use Android's "Clear data" function in app settings.

---

## 4. Permissions used and why

Android requires Aero to declare each permission it uses. Each one exists for a specific feature; nothing is collected for analytics or marketing.

| Permission | Why Aero needs it | Data leaving your phone? |
|---|---|---|
| `BLUETOOTH`, `BLUETOOTH_ADMIN` (legacy) | Connect to Arduino HC-05/HC-06 modules and to LEGO MINDSTORMS NXT and EV3 bricks. | No. Bluetooth traffic goes directly between your phone and the device you chose. |
| `BLUETOOTH_CONNECT` (Android 12+) | Same reason as above, on newer Android versions. | No. |
| `BLUETOOTH_SCAN` (Android 12+) | Discover BLE peripherals such as the HM-10 module or BLE-capable ESP32. Declared with `usesPermissionFlags="neverForLocation"` so Bluetooth scans cannot be used to derive your location. | No. |
| `ACCESS_FINE_LOCATION` | Required by Android itself in order for BLE scans to return results on Android 9–11. Aero never reads, stores, or transmits your GPS coordinates. | No. |
| `INTERNET`, `ACCESS_NETWORK_STATE`, `ACCESS_WIFI_STATE`, `CHANGE_WIFI_STATE` | Open a TCP socket to the IP address you type in (your ESP8266, ESP32, or ESP32-CAM). Detect whether you are on WiFi. Read the phone's own WiFi IP so it can be displayed on the home screen. | Only the commands you choose to send to the IP you typed in. Aero never contacts a server operated by the developer. |
| `CAMERA` | Display a viewfinder when controlling robots that include a phone-mounted camera (Robot mode), if you enable it. | No. The camera feed is rendered on-screen only. |
| `RECORD_AUDIO` | Power the optional **Voice Control** feature. The microphone is only opened while you are actively pressing or holding the voice button. | See Section 5. |
| `VIBRATE` | Tactile feedback for button presses. | No. |
| `HIGH_SAMPLING_RATE_SENSORS` | Smooth tilt-control response from the phone's accelerometer. | No. |
| `FOREGROUND_SERVICE`, `FOREGROUND_SERVICE_CONNECTED_DEVICE` | Keep the connection to the robot alive when you put the phone screen to sleep, and show a persistent notification while connected. | No. |
| `POST_NOTIFICATIONS` (Android 13+) | Show the persistent "connected" notification described above. | No. |
| `com.ainirobot.coreservice.robotSettingProvider` | Used only when Aero is installed on an OrionStar AI robot to access the robot's motion API. Has no effect on regular phones or tablets. | No. |

All Bluetooth and WiFi traffic stays on the local link: phone ↔ robot/microcontroller. Aero does not phone home.

---

## 5. Voice Control — clarification on speech recognition

The optional **Voice Control** mode uses Android's built-in `SpeechRecognizer` API. On most Android phones this is provided by Google Speech Services and may briefly send recorded audio to Google's servers for transcription. The transcribed text is then handed to Aero, which matches it against the command words you have configured locally.

Important points:

- Voice Control is off by default. You must explicitly enable it inside the app for it to listen.
- The microphone is only opened while you are actively in the Voice panel.
- Aero itself does not record, store, transmit, or analyse your audio. The processing is performed by Android's system speech-recognition component, which is governed by Google's privacy policy: <https://policies.google.com/privacy>.
- If you do not want any audio leaving your phone, do not enable Voice Control. All other features of Aero work without it.

---

## 6. Cameras and IP video streams

When you use **ESP32-CAM** mode or the **IP Camera** mode, Aero opens a video stream from the URL you typed in (typically a device on your local network). The stream is decoded and displayed in the app. It is not recorded, not stored, and not forwarded anywhere by Aero.

If you point Aero at a third-party MJPEG stream URL, that third party may have its own privacy policy that applies to the stream itself; Aero merely renders the frames on screen.

---

## 7. Children's privacy

Aero is suitable for general audiences. The app does not knowingly collect personal information from children under 13. Because Aero does not collect personal information from anyone, it does not collect it from children either.

The app does include user-supplied text fields (custom button labels, terminal input, etc.) that are stored locally on the device. Parents and educators are encouraged to supervise younger users in the same way they would for any tool that talks to electronics.

---

## 8. Third-party services

Aero does **not** include any of the following:

- Advertising SDKs (no AdMob, no Unity Ads, no Facebook Audience Network).
- Analytics SDKs (no Firebase Analytics, no Mixpanel, no Amplitude).
- Crash-reporting SDKs (no Firebase Crashlytics, no Sentry, no Bugsnag).
- Social-login SDKs.
- Any other SDK that contacts a remote service in the background.

The libraries linked into the app (`androidx.appcompat`, `material`, `gson`, `Java-WebSocket`) are open-source utilities used internally for UI, JSON parsing, and WebSocket communication on the local network. They do not connect to any third-party server.

The only system-level cloud touchpoint is described in Section 5 (Voice Control via Android speech recognition).

---

## 9. Data retention and deletion

Because no data is sent off your device, there is no remote copy to delete. To remove all local data:

- **Quick reset (preserves install):** Android Settings → Apps → Aero → Storage → "Clear data".
- **Full removal:** Uninstall Aero. Android removes the app's private storage automatically.

---

## 10. Security

All app data is stored in Android's per-app private storage area, isolated from other apps by the Android sandbox. Bluetooth pairing keys are managed by the Android system, not by Aero. Network traffic is local (phone to your robot on the same WiFi network or local Bluetooth link); the app does not establish outbound connections to the internet.

We recommend that you:

- Pair Bluetooth modules in a private place (Bluetooth pairing exposes your device to nearby scanners briefly).
- Use a private WiFi network when controlling ESP-based projects, since the protocol is plain text and unauthenticated.

---

## 11. Your rights

You can:

- See what permissions Aero has at any time in Android Settings → Apps → Aero → Permissions.
- Revoke any permission at any time from that same screen. The corresponding feature will simply be disabled.
- Delete all locally-stored data at any time using "Clear data" or uninstall.
- Stop using the app at any time without contacting the developer.

Because Aero does not store any of your data on a server, there is no remote account or profile for you to access, port, or delete. There is nothing to export.

---

## 12. Changes to this policy

If this policy is updated (for example, if a future version of Aero adds a feature that materially changes how data is handled), the new policy will be posted at the same URL where you found this one. The "Last Updated" date at the top will be revised. Material changes will also be noted in the GitHub release notes for the affected app version.

---

## 13. Contact

For questions about this Privacy Policy or Aero in general:

- **GitHub Issues (preferred):** <https://github.com/engrpanda/Aero_U-Robot-Link/issues>
- **Email:** engrpanda@gmail.com *(replace with your published contact email before submitting to Play Store)*

You can also report a bug or request a feature through the same GitHub Issues page.

---

*This Privacy Policy applies to the Aero (U-Robot Link) Android application distributed by Engr. J R Cabataña, ECT. It does not apply to robots, microcontrollers, or services manufactured by third parties (Arduino, Espressif, OrionStar, LEGO Group, etc.) which have their own privacy practices.*
