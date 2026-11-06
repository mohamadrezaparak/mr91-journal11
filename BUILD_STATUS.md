# Build status — 1.0.0-beta source handoff

- Android source project prepared.
- GitHub Actions workflow added at `.github/workflows/android-apk.yml`.
- Workflow builds a debug APK and uploads it as the `MR91-Journal-debug-APK` artifact.
- The source ZIP and workflow have not yet been executed by GitHub Actions.
- No APK is claimed to exist until GitHub reports a successful build and the artifact is downloaded.
- Physical-device QA, export/restore round-trip testing, exact MR91 website design audit, and production signing remain release gates.
