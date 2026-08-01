# Implementation Plan - Fix Build and Prepare for GitHub

The user wants to fix the code and make it "pushable to GitHub." The current project has a critical build failure due to an outdated `compileSdk` version and some minor state management issues in the UI.

## User Review Required

> [!IMPORTANT]
> I am upgrading the `compileSdk` and `targetSdk` to **37** to resolve dependency conflicts. This is required because the current versions of `androidx.core` and `androidx.lifecycle` in the project explicitly require API level 37.

## Proposed Changes

### Build Configuration

#### [MODIFY] [app/build.gradle.kts](file:///Volumes/Kaijo's%20512gb/cms%20github/app/build.gradle.kts)
- Update `compileSdk` and `targetSdk` to **37** (or the required release version) to fix the AAR metadata check error.

### Source Code

#### [MODIFY] [MainActivity.kt](file:///Volumes/Kaijo's%20512gb/cms%20github/app/src/main/java/com/example/myapplication/MainActivity.kt)
- Change `remember` to `rememberSaveable` for the `count` state so it survives configuration changes (like screen rotation).
- Add a `@Preview` function to enable UI inspection in Android Studio.
- Minor cleanup of imports and formatting.

### Project Hygiene

#### [MODIFY] [.gitignore](file:///Volumes/Kaijo's%20512gb/cms%20github/.gitignore)
- Add common missing entries for Kotlin and IDE artifacts to ensure a clean repository when pushed to GitHub.

#### [MODIFY] [README.md](file:///Volumes/Kaijo's%20512gb/cms%20github/README.md)
- Update with a proper project title and a brief description of the "Reactive Counter" functionality.

## Verification Plan

### Automated Tests
- Run `./gradlew app:assembleDebug` to verify the build now passes.

### Manual Verification
- Render the Compose Preview of `MainActivity.kt` to ensure the UI looks correct.
