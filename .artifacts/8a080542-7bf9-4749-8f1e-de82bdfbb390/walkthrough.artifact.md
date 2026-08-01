# Project Fixed and GitHub Ready

I have resolved the build issues, improved state management, and prepared the project for GitHub.

## Changes Made

### 1. Fixed Build Error (API 37 Upgrade)
The project was failing to build because the current dependencies require **Android API 37**. I updated `app/build.gradle.kts` to use `compileSdk = 37` and `targetSdk = 37`.

### 2. Improved State Management
In `MainActivity.kt`, I replaced `remember` with `rememberSaveable` for the counter state. This ensures the count is preserved during configuration changes, such as screen rotation.

### 3. Added Compose Preview
I added a `@Preview` function to `MainActivity.kt`, allowing you to visualize the UI directly in Android Studio without running the app.

![UI Preview](/Volumes/Kaijo's%20512gb/cms%20github/.artifacts/8a080542-7bf9-4749-8f1e-de82bdfbb390/preview.png)

### 4. GitHub Readiness
- **Comprehensive .gitignore**: Updated the root `.gitignore` to exclude standard IDE, build, and user-specific files, ensuring only source code is pushed to your repository.
- **Project Documentation**: Updated `README.md` with a clear title, feature list, and instructions on how to run the project.

## Verification Results

- [x] **Build**: Successfully executed `./gradlew app:assembleDebug`.
- [x] **UI**: Verified the layout using Compose Preview.
- [x] **State**: `rememberSaveable` implemented for counter and name.
