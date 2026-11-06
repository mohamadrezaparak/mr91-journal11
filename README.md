# MR91 Journal — Android MVP

A native Java, offline-first Android starter for a trading journal.

## Current implementation
- Local SQLite database (no account, no network permission)
- Add and list trades
- Search by symbol or strategy
- Delete trades with confirmation
- Dashboard trade count and net result
- Persian/English UI toggle
- Dark/light theme toggle
- Android native UI; no third-party runtime dependencies

## Build
- Android Studio
- JDK 17
- Android Gradle Plugin 8.7.3
- Gradle 8.9
- Android SDK 35

Open this folder in Android Studio and let Gradle sync. Build with **Build > Build Bundle(s) / APK(s) > Build APK(s)**.

## Important MVP limitations
This is the first runnable foundation, not the finished product. Trade editing, image attachments, robust statistics, export/import (PDF/CSV/JSON/ZIP), backup/restore, calendar, risk metrics, migrations, and automated tests are not implemented yet. Do not publish this build as a release.
