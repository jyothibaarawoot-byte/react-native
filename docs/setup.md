# Setup — Expo-first (recommended) and Bare React Native

This guide covers two approaches so learners can choose:

- Expo (recommended for beginners): fast onboarding, no native toolchain required for most examples.
- Bare React Native (recommended for learning native tooling or when you need custom native modules): requires Android Studio and/or Xcode.

## Quick choices

- If you're new: follow the Expo sections first — you'll be building apps faster.
- If you need native modules or want to learn platform tooling: follow the Bare React Native sections after you're comfortable with core concepts.

---

## Expo (managed) — get started quickly

Prerequisites

- Node.js LTS
- npm or yarn
- Expo CLI: npm install -g expo-cli
- Optional: Expo Go app on iOS/Android device

Run the included example

cd examples/hello-world
npm install
expo start

Open the QR code with Expo Go on your device or run in an emulator (Android Studio AVD or iOS Simulator).

Notes

- Expo's managed workflow avoids native build configuration. Use it for most learning modules.
- When you need native libraries that Expo doesn't provide, you can "prebuild" or eject to a bare project (`expo prebuild`) or create a separate bare example.

See docs/native-setup.md for emulator setup (Android Studio / Xcode).

---

## Bare React Native — learn the native toolchain

Prerequisites

- Node.js LTS
- npm or yarn
- Java JDK (11+ recommended)
- Android Studio (with Android SDK & AVD)
- Xcode (macOS only, for iOS)
- CocoaPods (for iOS): sudo gem install cocoapods or use Homebrew

Create a bare project (recommended way)

npx react-native init BareHelloWorld
cd BareHelloWorld

Install dependencies and run

# Android (device or AVD must be running)
npx react-native run-android

# iOS (macOS only)
cd ios
pod install
cd ..
npx react-native run-ios

Notes

- Use the examples/bare-hello-world README for a ready-to-run starting point included in this repository.
- For native modules or platform APIs not provided by Expo, use the bare workflow.

See docs/native-setup.md for detailed steps to install Android Studio and Xcode and configure emulators/simulators.
