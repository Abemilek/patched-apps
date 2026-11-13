# Patched Android Apps

Prebuilt APKs for Android, patched with [Morphe](https://morphe.software) and community patch bundles. No root required.

Download the builds from **[Releases](https://github.com/Abemilek/patched-apps/releases)**. Each release lists the exact patches, supported architecture, minimum Android version and SHA-256 checksum.

> Unofficial builds. Not affiliated with the app developers or patch authors. Use at your own risk.

## Available apps

| App | Version | Architecture | Patched with | Min Android |
| --- | --- | --- | --- | --- |
| [X](https://github.com/Abemilek/patched-apps/releases/tag/x-12.19.1) | 12.19.1 / 11.0.0 | arm64-v8a / armeabi-v7a | Piko 3.10.0 / 2.0.0 | 9.0 / 8.0 |
| [YouTube](https://github.com/Abemilek/patched-apps/releases/tag/youtube-20.21.37) | 20.21.37 | arm64-v8a, armeabi-v7a | Morphe 1.47.0 | 8.0 |
| [Instagram](https://github.com/Abemilek/patched-apps/releases/tag/instagram-447.0.0.55.81) | 447.0.0.55.81 / 423.0.0.47.66 | arm64-v8a / armeabi-v7a | Piko 3.10.0 / 3.2.0 | 9.0 / 8.0 |
| [Facebook](https://github.com/Abemilek/patched-apps/releases/tag/facebook-583.0.0.39.55) | 583.0.0.39.55 | arm64-v8a, armeabi-v7a | Hushfacebook 0.16.1 | 11.0 |
| [Facebook Lite](https://github.com/Abemilek/patched-apps/releases/tag/facebook-lite-536.0.0.11.107) | 536.0.0.11.107 | arm64-v8a, armeabi-v7a | BlazeFTL 1.6.7 + FTL 1.43.7.4 | 8.0 / 6.0 |
| [Gboard Lite](https://github.com/Abemilek/patched-apps/releases/tag/gboard-18.5.1) | 18.5.1.993608717 | arm64-v8a, armeabi-v7a | Kveld 2.10.1 | 8.1 |
| [Brave](https://github.com/Abemilek/patched-apps/releases/tag/brave-1.98.63) | 1.98.63 | arm64-v8a, armeabi-v7a | Kveld 2.10.1 | 10.0 |
| [Proton Mail](https://github.com/Abemilek/patched-apps/releases/tag/proton-mail-7.11.12) | 7.11.12 | arm64-v8a, armeabi-v7a, x86, x86_64 | hxreborn 1.73.0 + Kveld 2.10.1 | 29 |

## Installation

1. Check your CPU architecture:

   ```bash
   adb shell getprop ro.product.cpu.abilist
   ```

   Use the `arm64-v8a` build if it is listed, otherwise use `armeabi-v7a`.
2. Back up the data you want to keep.
3. Uninstall the official app first. These builds use a different signing key, so Android will not install them over the original.

   Exceptions that can coexist with the official app: patched YouTube (separate package), the arm64 Instagram build (Piko clone) and Gboard Lite (separate package).
4. Install the APK.

## App notes

- **YouTube:** install MicroG first (included in the YouTube release). The patched app uses the package `app.morphe.android.youtube`.
- **Instagram:** the arm64 build is a Piko clone and can coexist with the official app. The armv7 build replaces the official app.
- **Facebook:** requires Android 11 or newer.
- **Facebook Lite:** arm64-v8a requires Android 8.0+, armeabi-v7a requires Android 6.0+. Includes AMOLED resources for the dark theme, popups, splash and notifications; enable dark mode in the app. Server-provided colors and the video quality sheet may stay dark gray. Sponsored posts are hidden client-side and third-party analytics SDKs are removed, but Meta's own server-side telemetry cannot be fully disabled by patching.
- **Gboard Lite:** the offline build has no `INTERNET` permission. To download a language dictionary, install the `setup-online` build from the release, download the language, then install the offline build over it.
- **Brave:** after installing, open **Settings → General → Brave Origin** and disable Leo AI, VPN, Rewards, News and Wallet. Set **Appearance → Theme → Dark** to enable the AMOLED theme.

## Verification

Every release includes the SHA-256 of each APK. Compare it locally:

```bash
sha256sum <file.apk>
```

## Disclaimer

These builds are provided for personal use. All applications are property of their respective owners. The patch authors and this repository are not responsible for account bans, data loss or device damage.
