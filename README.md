# Patched Android Apps

Prebuilt APKs for Android, patched with [Morphe](https://morphe.software) and community patch bundles. No root required.

Download the builds from **[Releases](https://github.com/Abemilek/patched-apps/releases)**. Each release lists the exact patches, supported architecture, minimum Android version and SHA-256 checksum.

> Unofficial builds. Not affiliated with the app developers or patch authors. Use at your own risk.

## Available apps

| App | Version | Architecture | Patched with | Min Android |
| --- | --- | --- | --- | --- |
| X | 12.19.1 / 11.0.0 | arm64-v8a / armeabi-v7a | Piko 3.10.0 / 2.0.0 | 9.0 / 8.0 |
| YouTube | 20.21.37 | arm64-v8a, armeabi-v7a | Morphe 1.47.0 | 8.0 |
| Instagram | 447.0.0.55.81 / 423.0.0.47.66 | arm64-v8a / armeabi-v7a | Piko 3.10.0 / 3.2.0 | 9.0 / 8.0 |
| Facebook | 583.0.0.39.55 | arm64-v8a, armeabi-v7a | Hushfacebook 0.16.1 | 11.0 |
| Gboard Lite | 18.5.1.993608717 | arm64-v8a, armeabi-v7a | Kveld 2.10.1 | 8.1 |
| Brave | 1.98.63 | arm64-v8a, armeabi-v7a | Kveld 2.10.1 | 10.0 |

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
- **Gboard Lite:** the offline build has no `INTERNET` permission. To download a language dictionary, install the `setup-online` build from the release, download the language, then install the offline build over it.
- **Brave:** after installing, open **Settings → General → Brave Origin** and disable Leo AI, VPN, Rewards, News and Wallet. Set **Appearance → Theme → Dark** to enable the AMOLED theme.

## Verification

Every release includes the SHA-256 of each APK. Compare it locally:

```bash
sha256sum <file.apk>
```

## Disclaimer

These builds are provided for personal use. All applications are property of their respective owners. The patch authors and this repository are not responsible for account bans, data loss or device damage.
