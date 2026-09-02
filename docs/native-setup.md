# Native toolchain setup — Android Studio & Xcode (intro)

This page gives a concise walkthrough for setting up Android Studio (Android SDK/AVD) and Xcode for React Native development.

Android Studio (Windows / macOS / Linux)

1. Install Android Studio from https://developer.android.com/studio
2. During install, ensure the Android SDK, SDK Platform tools, and Android SDK Build-Tools are installed.
3. Open Android Studio → SDK Manager and install recommended SDK versions (we recommend API 31+).
4. Create an AVD (Android Virtual Device) in AVD Manager. Pick a Play Store image or a Google APIs image for wide compatibility.
5. Ensure environment variables:
   - ANDROID_HOME or ANDROID_SDK_ROOT pointing to your SDK path
   - Add $ANDROID_SDK_ROOT/platform-tools to your PATH

Troubleshooting

- If `adb` is not found, ensure platform-tools are installed and PATH is set.
- On Linux, install required dependencies for emulator acceleration (KVM).

Xcode (macOS only)

1. Install Xcode from the App Store (or from developer.apple.com for beta versions).
2. Open Xcode once to accept the license and finish setup.
3. Install Xcode command line tools: xcode-select --install
4. Install CocoaPods if you haven't: sudo gem install cocoapods or brew install cocoapods
5. For iOS projects created by the React Native CLI, run `pod install` in the ios/ directory before building.

Simulators and devices

- iOS: use Simulator from Xcode (Hardware → Device) or attach a physical device and enable developer mode.
- Android: run an AVD from Android Studio or use a physical device with USB debugging enabled.

Notes on macOS and iOS builds

- Building for iOS requires a macOS machine with Xcode installed.
- For publishing to the App Store you'll need an Apple Developer account and proper provisioning profiles and certificates (see docs/deployment.md).
