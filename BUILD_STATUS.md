# Build status — MR91 Journal 1.1.0-beta

- Source updated from the latest GitHub-ready 1.0.0-beta project.
- App version: `1.1.0-beta` (`versionCode 4`).
- Database schema: version 3.
- GitHub Actions workflow retains the patched SDK setup that avoids the obsolete `sdkmanager tools` package.
- This environment does not have Android SDK/Gradle installed, so no APK build is claimed.
- Next verification: push this source to GitHub, run Actions, inspect the Gradle build result, then install and test the APK on a real Android device.
