# MR91 Journal — Android 1.1.0-beta

Native Java trading journal, designed for offline use.

## Features
- Trade CRUD with entry/exit, stop/target, size, result, fees, strategy, timeframe, emotion, notes and status.
- Local image attachments, private app storage and preview.
- Dashboard, win rate, net result, average price-move/risk ratio and strategy breakdown.
- Search and date filters.
- PDF, CSV and JSON exports; full ZIP backup/restore including the SQLite database and trade images.
- Persian/English UI, RTL/LTR, dark/light palette.
- Offline risk calculator, daily pre-trade checklist and SQLite-backed daily review.
- No account, no network permission, no third-party runtime dependencies.

## Stack
- Java / native Android UI
- Android Gradle Plugin 8.7.3, Gradle 8.9, JDK 17
- compileSdk/targetSdk 35, minSdk 23
- SQLite schema version 3

## Build
Open the project in Android Studio with JDK 17 and Android SDK 35. Or use the GitHub Actions workflow in `.github/workflows/android-apk.yml`; it builds a debug APK and uploads it as an artifact.

## Important
The risk calculator reports a cash risk amount and a simplified linear units estimate. It is not a broker-specific lot calculator and does not model contract size, pip value, leverage, spread, swaps or currency conversion. Confirm position sizing independently.

This is a beta. The source has received static review and limited local checks, but the Android build, installation, upgrade, backup/restore and real-device UI tests still need to pass before release.
