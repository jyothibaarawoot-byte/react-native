# Bare React Native example (README)

This folder contains a minimal App.js and guidance for running a bare React Native project (react-native CLI).

To create a matching bare project locally

1. Create the project using the React Native CLI:

   npx react-native init BareHelloWorld

2. Replace the generated `App.js` with the `App.js` from this folder (or copy the contents).
3. Install CocoaPods for iOS (macOS only):

   cd ios && pod install && cd ..

4. Run on Android (ensure an emulator or device is connected):

   npx react-native run-android

5. Run on iOS (macOS only):

   npx react-native run-ios

Notes

- The bare workflow requires Android Studio and/or Xcode for building native apps. See docs/native-setup.md for setup instructions.
- When adding native libraries, follow each library's installation instructions and run `pod install` for iOS.
