# BAI-ONE Android — Phone-first next steps

This package is an Android Studio source project, not an APK installer yet.

## What is already in the project

- Android launcher app named **BAI-ONE** (`com.baione.memory`)
- The Prototype 001 memory interface bundled inside the app
- Local memory storage on the device
- Search, categories, and memory deletion
- Encrypted `.bai` backup and restore using the Android file picker
- GitHub Actions workflow at `.github/workflows/android.yml` to build a debug APK in the cloud

## What is not finished yet

- The APK has not been compiled or tested on a physical phone.
- There is no login, automatic cloud sync, multi-device sharing, or AI conversation feature yet.
- The app currently keeps memories on the device. Users should create encrypted backups regularly.

## Build the APK without owning a computer

The easiest computer-free route is to use a GitHub repository and its Actions build service. You will need a GitHub account and must upload the *contents* of this project into a new repository while preserving the folder structure (especially `.github/workflows/android.yml`). Then:

1. Open the repository on GitHub.
2. Open **Actions** and enable workflows if GitHub asks.
3. Choose **Build BAI-ONE Android APK**.
4. Tap **Run workflow**.
5. Wait for the workflow to finish successfully.
6. Open the completed workflow run and download the `BAI-ONE-debug-apk` artifact.
7. Extract the downloaded artifact ZIP on your Android phone. It contains `app-debug.apk`.
8. Open the APK and follow Android's install prompts. Android may ask you to allow installs from the browser or file manager you used.

If you cannot upload the folders while using GitHub on your phone, do not upload only this ZIP and expect Actions to build it: the workflow must be present at `.github/workflows/android.yml` in the repository root structure. We can work through the upload route together.

## Safety and release note

For early personal testing, the debug APK is suitable. Before distributing BAI-ONE publicly, we should create a signed release build, test backup/restore and data retention on multiple Android devices, and publish a privacy policy. Never share your backup passphrase. If it is lost, the encrypted backup cannot be restored.
