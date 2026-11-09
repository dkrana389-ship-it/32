# Call Report – Android project

## GitHub Actions APK build

This project includes `.github/workflows/build-apk.yml`. Upload the **contents of this ZIP** to the root of your GitHub repository (not the enclosing folder), commit to `main`, then open **Actions**. The workflow builds a debug APK and uploads it as the `CallReport-debug-apk` artifact.

## Build configuration

- JDK 17
- Gradle 8.9 (downloaded by the workflow; no Gradle wrapper is required)
- Android compile SDK 35 / build tools 35.0.0
- Google Mobile Ads SDK with Google's official sample test App ID and banner ad unit ID

## AdMob testing

The project uses Google's official test IDs. Test ads are for development only and do not generate revenue. Replace the sample App ID in `app/src/main/AndroidManifest.xml` and the sample banner unit ID in `CallReportActivity.kt` with your own IDs only after testing and following AdMob policies.

## Important Android behavior

The app requests the Call Screening role and call-related permissions. Automatic post-call UI behavior depends on Android version, device/OEM implementation, and the user granting the role. Verify on a physical device; a successful APK build does not guarantee the system will launch the post-call activity on every device.
