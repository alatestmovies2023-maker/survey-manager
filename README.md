# KCGROUP LTD - Offline Survey App

Clean-room Android project based on the supplied survey-screen requirements. It does **not** modify or bypass the original APK's device-whitelist mechanism.

## Included
- Society, Developer Name, Location, Biometric Done by
- Reference Number, Tenant Name, Occupant Name, Mobile
- ID Type + ID Number
- Length, Breadth, Carpet Possession Area, Remark
- Take Photo / Take Video
- Unlimited photo and video captures (no app-imposed count limit)
- Left Thumb / Right Thumb UI
- Fully offline data entry
- Saves JSON survey data and media under:
  `/storage/emulated/0/WORK/KCGROUP LTD/Local Data/Survey_<timestamp>/`
- Each survey gets `survey.json`, `Photos/`, and `Videos/`
- No server/API/network dependency

## Important Android storage note
On Android 11 and newer, the project requests the Android "All files access" special permission so the app can write directly to the requested top-level `WORK` folder. This is appropriate for a controlled/sideloaded field-survey deployment but is subject to Android/Google Play policy if distributed through Play Store.

## Biometric note
The original APK contains vendor-specific native biometric libraries. This clean-room build intentionally does not copy those proprietary libraries or pretend to produce a fingerprint template. The Left Thumb / Right Thumb UI is present, and the buttons can mark the field as captured. To capture actual Mantra/other scanner fingerprints, the exact scanner model and licensed SDK must be integrated separately.

## Build
Open this folder in Android Studio and let it sync/download the Android Gradle Plugin. Then choose:
`Build > Generate App Bundles or APKs > Generate APKs`.

Minimum Android version: 6.0 (API 23)
Target SDK: 35

## Runtime
Internet is not required. Camera/video use the device camera application. Data is stored locally.
