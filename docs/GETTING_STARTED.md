# Getting Started - Run on Your Phone

This guide will help you run the Flutter Password Manager UI app on your Android or iOS phone.

---

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Method 1: Run on Android Phone (Developer Mode)](#method-1-run-on-android-phone-developer-mode)
3. [Method 2: Run on iOS Phone (Developer Mode)](#method-2-run-on-ios-phone-developer-mode)
4. [Method 3: Install Pre-built APK (Android Only)](#method-3-install-pre-built-apk-android-only)
5. [Method 4: Build and Install APK (Android)](#method-4-build-and-install-apk-android)
6. [Troubleshooting](#troubleshooting)

---

## Prerequisites

### Required Software

1. **Flutter SDK** (3.7.0 or higher)

   - Download from: https://flutter.dev/docs/get-started/install
   - Verify installation: `flutter --version`

2. **Git** (for cloning the repository)

   - Download from: https://git-scm.com/downloads

3. **Code Editor** (choose one)
   - Visual Studio Code: https://code.visualstudio.com/
   - Android Studio: https://developer.android.com/studio

### For Android Development

4. **Android Studio** (for Android SDK)

   - Download: https://developer.android.com/studio
   - Install Android SDK Platform-Tools
   - Install Android SDK Build-Tools

5. **USB Cable** (to connect your phone to computer)

### For iOS Development (macOS only)

6. **Xcode** (latest version)

   - Download from Mac App Store
   - Install Xcode Command Line Tools

7. **CocoaPods** (dependency manager)
   ```bash
   sudo gem install cocoapods
   ```

---

## Method 1: Run on Android Phone (Developer Mode)

This is the **recommended method** for development and testing.

### Step 1: Set Up Your Android Phone

1. **Enable Developer Options**

   - Go to **Settings** > **About Phone**
   - Find **Build Number**
   - Tap **Build Number** 7 times
   - You'll see "You are now a developer!"

2. **Enable USB Debugging**

   - Go to **Settings** > **System** > **Developer Options**
   - Turn on **USB Debugging**
   - Accept any security warnings

3. **Connect Phone to Computer**
   - Use a USB cable to connect your phone
   - On your phone, allow USB debugging when prompted
   - Select "Always allow from this computer" (optional)

### Step 2: Verify Phone Connection

Open terminal/command prompt and run:

```bash
flutter devices
```

You should see your Android device listed like:

```
Galaxy S21 (mobile) • 1234567890ABCDEF • android-arm64 • Android 12 (API 31)
```

### Step 3: Install Dependencies

Navigate to the project folder:

```bash
cd "C:\Work\100 projects\Project_10\flutter-password-manager-ui"
```

Install Flutter packages:

```bash
flutter pub get
```

### Step 4: Run the App

**Option A: Using Command Line**

```bash
flutter run
```

The app will:

- Compile the code
- Install on your connected phone
- Launch automatically

**Option B: Using Visual Studio Code**

1. Open the project folder in VS Code
2. Press **F5** or click **Run > Start Debugging**
3. Select your Android device from the device picker

**Option C: Using Android Studio**

1. Open the project in Android Studio
2. Select your device from the device dropdown
3. Click the green **Run** button (▶)

### Step 5: App is Running!

- The app should now be running on your phone
- You can interact with it directly
- Hot reload works: Press `r` in terminal to reload changes

---

## Method 2: Run on iOS Phone (Developer Mode)

**Requirements:** macOS computer, Xcode, Apple Developer account (free or paid)

### Step 1: Set Up Xcode

1. **Open Xcode**
2. Go to **Xcode > Preferences > Accounts**
3. Add your Apple ID
4. Sign in with your Apple ID

### Step 2: Configure iOS Project

Navigate to the iOS folder:

```bash
cd "C:\Work\100 projects\Project_10\flutter-password-manager-ui\ios"
```

Install CocoaPods dependencies:

```bash
pod install
```

### Step 3: Open in Xcode

```bash
open Runner.xcworkspace
```

In Xcode:

1. Select **Runner** in the project navigator
2. Go to **Signing & Capabilities**
3. Select your **Team** (your Apple ID)
4. Change **Bundle Identifier** to something unique (e.g., `com.yourname.passwordmanager`)

### Step 4: Trust Developer on iPhone

1. Connect iPhone via USB cable
2. On iPhone: **Settings** > **General** > **Device Management**
3. Trust the developer certificate

### Step 5: Run the App

Return to the project root:

```bash
cd ..
flutter run
```

Or use Xcode:

1. Select your iPhone from the device dropdown
2. Click the **Run** button (▶)

---

## Method 3: Install Pre-built APK (Android Only)

The easiest method if you just want to install and use the app.

### Step 1: Download APK

Download the pre-built APK from:

- **GitHub Repository:** Check the releases section
- **Direct Link:** https://mega.nz/file/jxtHnRII#9EhtKDjHgcidu5od_4TR8v3BHwOe68IOX--r5NE57r8

### Step 2: Enable Unknown Sources

On your Android phone:

1. Go to **Settings** > **Security** (or **Apps & notifications**)
2. Enable **Install from Unknown Sources**
   - Or allow installation from your browser/file manager

### Step 3: Install APK

1. Open the downloaded APK file
2. Tap **Install**
3. Wait for installation to complete
4. Tap **Open** to launch the app

### Step 4: Launch App

- Find "Password Manager" in your app drawer
- Tap to open and use

---

## Method 4: Build and Install APK (Android)

Build your own APK from source code.

### Step 1: Navigate to Project

```bash
cd "C:\Work\100 projects\Project_10\flutter-password-manager-ui"
```

### Step 2: Install Dependencies

```bash
flutter pub get
```

### Step 3: Build APK

**For Debug APK (faster, larger file):**

```bash
flutter build apk --debug
```

**For Release APK (optimized, smaller file):**

```bash
flutter build apk --release
```

**For Split APKs (separate files for different architectures):**

```bash
flutter build apk --split-per-abi
```

### Step 4: Locate APK File

The APK will be created in:

```
build/app/outputs/flutter-apk/app-release.apk
```

Full path:

```
C:\Work\100 projects\Project_10\flutter-password-manager-ui\build\app\outputs\flutter-apk\app-release.apk
```

### Step 5: Transfer to Phone

**Option A: USB Cable**

1. Connect phone via USB
2. Copy APK to phone's Downloads folder
3. Use file manager on phone to install

**Option B: Cloud Storage**

1. Upload APK to Google Drive, Dropbox, etc.
2. Download on phone
3. Install from Downloads

**Option C: Email**

1. Email the APK to yourself
2. Open email on phone
3. Download and install

**Option D: ADB (Advanced)**

```bash
adb install build/app/outputs/flutter-apk/app-release.apk
```

---

## Troubleshooting

### Common Issues and Solutions

#### 1. "flutter: command not found"

**Problem:** Flutter is not installed or not in PATH

**Solution:**

- Install Flutter: https://flutter.dev/docs/get-started/install
- Add Flutter to PATH:
  - Windows: Add `C:\flutter\bin` to PATH
  - macOS/Linux: Add to `~/.bashrc` or `~/.zshrc`

**Verify:**

```bash
flutter doctor
```

---

#### 2. "No devices detected"

**Problem:** Phone not recognized by computer

**Solution for Android:**

1. Enable USB Debugging (see Method 1, Step 1)
2. Change USB connection mode to "File Transfer" or "PTP"
3. Try a different USB cable (some cables are charge-only)
4. Install device drivers (Windows)
5. Restart ADB:
   ```bash
   adb kill-server
   adb start-server
   ```

**Solution for iOS:**

1. Trust computer on iPhone
2. Run: `flutter doctor` to check setup
3. Restart Xcode

---

#### 3. "App installation failed"

**Problem:** Installation blocked or failed

**Solution for Android:**

1. Uninstall existing version:
   ```bash
   adb uninstall com.example.password_manager
   ```
2. Enable "Install from Unknown Sources"
3. Clear Google Play Protect cache
4. Check available storage space

**Solution for iOS:**

1. Delete existing app from iPhone
2. Verify signing certificate in Xcode
3. Clean build: `flutter clean` then `flutter run`

---

#### 4. "Gradle build failed"

**Problem:** Android build errors

**Solution:**

1. Update Gradle:

   - Edit `android/gradle/wrapper/gradle-wrapper.properties`
   - Use Gradle 7.0 or higher

2. Clean and rebuild:

   ```bash
   cd android
   ./gradlew clean
   cd ..
   flutter clean
   flutter pub get
   flutter run
   ```

3. Check Java version:
   ```bash
   java -version
   ```
   Should be Java 11 or higher

---

#### 5. "CocoaPods not installed" (iOS)

**Problem:** Missing iOS dependencies

**Solution:**

```bash
sudo gem install cocoapods
pod setup
cd ios
pod install
cd ..
flutter run
```

---

#### 6. "Signing certificate error" (iOS)

**Problem:** Code signing issues

**Solution:**

1. Open `ios/Runner.xcworkspace` in Xcode
2. Select **Runner** > **Signing & Capabilities**
3. Choose your team
4. Change Bundle Identifier to unique value
5. Select "Automatically manage signing"

---

#### 7. "Multiple devices connected"

**Problem:** Flutter doesn't know which device to use

**Solution:**
Specify device ID:

```bash
flutter devices  # List all devices
flutter run -d DEVICE_ID  # Use specific device
```

Example:

```bash
flutter run -d 1234567890ABCDEF
```

---

#### 8. "Execution failed for task ':app:lintVitalRelease'"

**Problem:** Lint errors in release build

**Solution:**
Edit `android/app/build.gradle`:

```gradle
android {
    lintOptions {
        checkReleaseBuilds false
        abortOnError false
    }
}
```

---

#### 9. App crashes on startup

**Problem:** Runtime errors

**Solution:**

1. Check Flutter version compatibility:

   ```bash
   flutter doctor
   ```

2. View device logs:

   ```bash
   flutter logs
   ```

3. Run in debug mode to see error details:

   ```bash
   flutter run --debug
   ```

4. Clear app data on phone

---

#### 10. "Out of memory" error

**Problem:** Build process runs out of memory

**Solution:**
Edit `android/gradle.properties`:

```properties
org.gradle.jvmargs=-Xmx4096m -XX:MaxPermSize=512m
```

---

## Quick Reference Commands

### Check Flutter Setup

```bash
flutter doctor
flutter doctor -v  # Verbose output
```

### List Connected Devices

```bash
flutter devices
adb devices  # Android only
```

### Install Dependencies

```bash
flutter pub get
flutter pub upgrade  # Update packages
```

### Clean Build

```bash
flutter clean
flutter pub get
flutter run
```

### Run App

```bash
flutter run                    # Debug mode
flutter run --release          # Release mode
flutter run -d DEVICE_ID       # Specific device
```

### Build APK

```bash
flutter build apk --debug      # Debug APK
flutter build apk --release    # Release APK
flutter build apk --split-per-abi  # Split APKs
```

### Install via ADB

```bash
adb install path/to/app.apk
adb install -r path/to/app.apk  # Reinstall
```

### Uninstall App

```bash
adb uninstall com.example.password_manager
```

### View Logs

```bash
flutter logs
adb logcat  # Android logs
```

---

## Performance Tips

### Faster Build Times

1. **Enable Gradle Daemon**

   Edit `android/gradle.properties`:

   ```properties
   org.gradle.daemon=true
   org.gradle.parallel=true
   org.gradle.configureondemand=true
   ```

2. **Use Release Mode for Testing**

   ```bash
   flutter run --release
   ```

3. **Clear Cache Periodically**
   ```bash
   flutter clean
   ```

### Reduce APK Size

1. **Split by ABI**

   ```bash
   flutter build apk --split-per-abi
   ```

2. **Enable Proguard** (Android)

   Edit `android/app/build.gradle`:

   ```gradle
   buildTypes {
       release {
           minifyEnabled true
           shrinkResources true
       }
   }
   ```

---

## Additional Resources

### Official Documentation

- Flutter Installation: https://flutter.dev/docs/get-started/install
- Flutter Deploy: https://flutter.dev/docs/deployment
- Android Setup: https://developer.android.com/studio/debug/dev-options
- iOS Setup: https://developer.apple.com/documentation/xcode

### Video Tutorial

- Watch the speed coding video: https://www.youtube.com/watch?v=TlOu8205eaU

### Community Support

- Flutter Discord: https://discord.gg/flutter
- Stack Overflow: https://stackoverflow.com/questions/tagged/flutter
- GitHub Issues: https://github.com/RohanArora13/flutter-password-manager-ui/issues

---

## Platform-Specific Notes

### Android Requirements

- Minimum SDK: Android 5.0 (API 21)
- Target SDK: Latest stable
- Architecture: ARM64, ARMv7, x86_64

### iOS Requirements

- Minimum iOS: 11.0 or higher
- Requires macOS for development
- Apple Developer account (free tier works)

### Device Compatibility

- Works on all Android phones (5.0+)
- Works on iPhone 5S and newer
- Tablets supported
- Web version available (experimental)

---

## Next Steps After Installation

Once the app is running on your phone:

1. **Explore the UI**

   - Browse the home screen
   - View password categories
   - Check the password list

2. **Test Features**

   - Tap the + button to open add password modal
   - Fill in the form fields
   - Browse different sections

3. **Understand Limitations**

   - Remember this is a UI demo
   - Data is not persisted
   - Security features not implemented
   - See `docs/PROJECT_OVERVIEW.md` for details

4. **Start Developing** (Optional)
   - Enable hot reload for instant updates
   - Modify UI in code editor
   - See changes immediately on phone
   - Check `README.md` for contribution guidelines

---

## Summary

**Fastest Method:**

- Download pre-built APK → Install on Android phone

**Best for Development:**

- Method 1 (Run on Android via USB) with hot reload

**Best for iOS:**

- Method 2 (Xcode + Flutter)

**Most Control:**

- Method 4 (Build your own APK)

Choose the method that best fits your needs and technical comfort level!

---

**Need Help?**

- Check the [Troubleshooting](#troubleshooting) section
- Open an issue on GitHub
- Watch the video tutorial
- Refer to `docs/PROJECT_OVERVIEW.md` for project details

---

_Last Updated: January 2026_
_Flutter Version: 3.7.0+_
