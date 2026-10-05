<!-- SPDX-License-Identifier: MIT -->

# Shri Govind Auto OTP Copy

> यह मेरा एक एंड्रॉइड एप्लिकेशन है, जिसे मैंने ओपन-सोर्स कोड की मदद से कस्टमाइज़ किया है। यह ऐप आपके फोन पर आने वाले SMS और पुश नोटिफिकेशन से वन-टाइम पासवर्ड (OTP) को तुरंत डिटेक्ट करके स्क्रीन पर एक छोटा ओवरले दिखाता है, जिससे आप एक टैप में कोड कॉपी कर सकते हैं।

## मुख्य फीचर्स (Key Features)

- **ऑन-डिवाइस प्रोसेसिंग:** ऐप पूरी तरह से आपके फोन पर काम करता है। इसमें कोई इंटरनेट परमिशन नहीं है, कोई एनालिटिक्स नहीं है, और आपका डेटा पूरी तरह सुरक्षित है।
- **स्मार्ट ओवरले:** जब भी कोई OTP आएगा, स्क्रीन पर एक फ्लोटिंग कार्ड दिखेगा जो एक्टिव ऐप (जैसे बैंकिंग या शॉपिंग ऐप) के ऊपर रहेगा।
- **आसान कॉपी-पेस्ट:** सिर्फ एक टैप करके कोड कॉपी करें और एक्सेसिबिलिटी सर्विस की मदद से सीधे इनपुट फील्ड में पेस्ट करें।
- **प्राइवेसी फोकस्ड:** ऐप ऑटोमैटिकली आपके फोन नंबर और संवेदनशील जानकारी को छुपा देता है।
> A small Android overlay that surfaces one-time codes from SMS
> and push notifications on top of the foreground app, copies
> them on tap, and (optionally) auto-pastes into the OTP field
> via the Accessibility Service. Everything runs **on-device** —
> no network, no analytics, no third-party SDKs.

<p align="center">
  <img alt="Shri Govind Auto OTP Copy demo" src="https://github.com/MidTano/otp-overlay/releases/download/media/demo.webp" width="320">
</p>
  <a href="LICENSE"><img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-2ea44f?style=for-the-badge&logo=opensourceinitiative&logoColor=white"></a>
</p>

<p align="center">
  <a href="app/build.gradle.kts"><img alt="min-sdk" src="https://img.shields.io/badge/min--sdk-23-3DDC84?style=flat-square&logo=android&logoColor=white"></a>
  <a href="app/build.gradle.kts"><img alt="target-sdk" src="https://img.shields.io/badge/target--sdk-36-3DDC84?style=flat-square&logo=android&logoColor=white"></a>
  <a href="gradle/libs.versions.toml"><img alt="Kotlin" src="https://img.shields.io/badge/Kotlin-2.3.20-7F52FF?style=flat-square&logo=kotlin&logoColor=white"></a>
  <a href="gradle/libs.versions.toml"><img alt="AGP" src="https://img.shields.io/badge/AGP-9.2.1-1F6FEB?style=flat-square&logo=gradle&logoColor=white"></a>
  <a href="gradle/wrapper/gradle-wrapper.properties"><img alt="Gradle" src="https://img.shields.io/badge/Gradle-9.5.1-02303A?style=flat-square&logo=gradle&logoColor=white"></a>
  <a href="gradle.properties"><img alt="JDK" src="https://img.shields.io/badge/JDK-21-ED8B00?style=flat-square&logo=openjdk&logoColor=white"></a>
</p>

<p align="center">
  <a href="gradle/libs.versions.toml"><img alt="Lottie" src="https://img.shields.io/badge/Lottie-6.7.1-00DDB3?style=flat-square&logo=airbnb&logoColor=white"></a>
  <a href="gradle/libs.versions.toml"><img alt="Coroutines" src="https://img.shields.io/badge/Coroutines-1.11.0-7F52FF?style=flat-square&logo=kotlin&logoColor=white"></a>
  <a href="config/detekt/detekt.yml"><img alt="Detekt" src="https://img.shields.io/badge/Detekt-1.23.8-4279F7?style=flat-square"></a>
  <a href="app/build.gradle.kts"><img alt="JaCoCo" src="https://img.shields.io/badge/JaCoCo-0.8.13-D32F2F?style=flat-square"></a>
  <a href="gradle/libs.versions.toml"><img alt="Robolectric" src="https://img.shields.io/badge/Robolectric-4.16.1-0A8754?style=flat-square"></a>
  <a href="gradle/libs.versions.toml"><img alt="Espresso" src="https://img.shields.io/badge/Espresso-3.7.0-3DDC84?style=flat-square&logo=android&logoColor=white"></a>
  <a href="gradle/libs.versions.toml"><img alt="Mockito" src="https://img.shields.io/badge/Mockito-5.23.0-25A162?style=flat-square"></a>
</p>

<<p align="center">
  <strong>Built with the help of an awesome animated emoji pack —
  please give the original author some love.</strong>
</p>

<p align="center">
  <a href="https://t.me/addemoji/KawaiiEmoji">
    <img alt="Install KawaiiEmoji on Telegram" src="https://img.shields.io/badge/💖%20Install%20KawaiiEmoji%20pack%20on%20Telegram-26A5E4?style=for-the-badge&logo=telegram&logoColor=white&labelColor=0088CC">
  </a>
</p>

## Why

OTP codes still arrive as plain SMS or push notifications, and
the bank / marketplace / messenger expects you to memorise six
digits in three seconds before the banner rolls off. This app
flips the order:

- The overlay **stays on top of the active app** (banking,
  login, checkout) for the full window the user needs.
- One tap to copy, one accessibility paste to drop the code
  straight into the input field — no manual typing, no shade
  pull-down.
- The original heads-up notification can be silenced or replaced
  with a quiet shade-only mirror so the screen flash does not
  break flow.

## Privacy by construction

| Concern | What we do |
|---|---|
| OTP value | Never persisted. Logged as `***N digits` in the diagnostic; redacted on disk. |
| Sender / phone number | Long digit runs masked as `***N-digit-phone`; sender labels redacted in the rolling diagnostic. |
| Notification body | Stored in the `Last notification` diagnostic with all OTP-shaped digit runs masked before the body crosses a thread boundary. |
| Backups | `allowBackup="false"` — user-tuned regex / trigger words / stats never leave the device on a Google Drive backup or a phone-transfer. |
| Network | None. The app declares no `INTERNET` permission. |
| Logs | Stored under `filesDir` (sandboxed). The user can export through Settings → Logs for bug reports; nothing leaves the device automatically. |

## Permissions

| Permission | What it lets the app do |
|---|---|
| Display over other apps | Draw the OTP card on top of the foreground app. |
| Receive SMS | Catch incoming SMS via the platform broadcast. `READ_SMS` is **not** declared — the app never queries `content://sms`. |
| Notification access | Read posted notifications to extract OTPs delivered via push. |
| Accessibility (optional) | Auto-paste the code into the focused field. The user opts in. |


## Credits & License

This project is a fork of the original open-source application **[OTP Overlay](https://github.com/MidTano/otp-overlay)** developed by **[MidTano](https://github.com/MidTano)**. 

- **Original Repository:**
  .(https://github.com/MidTano/otp-overlay).
- **License:** MIT License

We have modified the application name and built it using automated GitHub Actions CI/CD workflows. All original code structure, privacy designs, and core functionalities belong to the original author.



*कृतज्ञता नोट: इस ऐप के सभी कोर फंक्शन्स और बेहतरीन प्राइवेसी आर्किटेक्चर का पूरा क्रेडिट इसके मूल लेखक (MidTano) को जाता है। हमने केवल इसके नाम और बिल्ड एनवायरनमेंट में बदलाव किए हैं।*
