# Deployment — Expo and Bare React Native (overview)

This guide gives a high-level overview of deployment options and recommended workflows for publishing apps to Google Play and the App Store.

Expo managed workflow

- Build and submit with EAS (Expo Application Services): https://docs.expo.dev/eas/
  - EAS Build creates APK/AAB (Android) and IPA (iOS) in the cloud.
  - EAS Submit can upload builds to Google Play and App Store Connect.
- For simple apps, use EAS Build; it handles credentials and reduces local setup complexity.

Example: build an Android AAB with EAS

1. npm install -g eas-cli
2. eas login
3. eas build --platform android --profile production

Bare React Native

Android (Play Store)

1. Generate a signed app bundle (AAB) using Gradle or Android Studio.
2. Create a keystore and configure signing in android/gradle.properties and build.gradle.
3. Build an AAB: cd android && ./gradlew bundleRelease
4. Upload the AAB to Google Play Console and follow the release steps.

iOS (App Store)

1. Ensure your app has a proper bundle identifier and provisioning profiles.
2. In Xcode, archive the app (Product → Archive) and export for App Store distribution.
3. Upload via Xcode Organizer or the Transporter app to App Store Connect.
4. Create a TestFlight beta and submit to TestFlight for internal/external testers before release.

Common tooling

- Fastlane helps automate signing, building, and submitting to stores. It's commonly used with CI for repeatable releases.
- Use GitHub Actions or other CI to automate builds, run tests, and optionally publish to internal distribution channels.

Guidelines and checks before publishing

- Test extensively on real devices and on both release and debug builds.
- Follow Play Store and App Store guidelines (privacy, content, permissions).
- Prepare store listing assets: app icons, screenshots for supported devices, privacy policy URL, contact info.

Security & credentials

- Keep keystores, signing keys, and Apple certificates secure — do not commit them to the repo.
- Use secrets in CI (GitHub Actions secrets, EAS secrets, or Fastlane match) to manage credentials safely.

Further reading

- Expo EAS docs: https://docs.expo.dev/eas/
- Android publishing: https://developer.android.com/studio/publish
- iOS publishing: https://developer.apple.com/app-store/
