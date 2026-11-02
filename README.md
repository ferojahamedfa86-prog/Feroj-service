# Feroj Service — Android source project

This is the current Android starter project for **Feroj Service**, intended for local-service discovery in Cooch Behar / West Bengal.

## Included now
- Kotlin + Jetpack Compose Android app
- Firebase project configuration (`feroj-service`)
- Firebase Email/Password account creation and sign-in
- Customer and worker account roles
- Service category browsing
- Worker profile submission with pending approval status
- Customer discovery of approved worker profiles
- Customer booking request creation and booking list
- Initial Firestore security rules
- GitHub Actions workflow to build and upload a debug APK artifact

## Important: current completion status
This is **not yet a finished production app** and no APK has been built or device-tested in this environment. The current app is a functional starter, not a complete marketplace.

Still required before public launch:
- Worker incoming-booking screen and accept/reject/complete workflow
- Secure admin approval/dashboard and admin provisioning
- Phone OTP authentication (Email/Password is currently configured)
- Wallet ledger and payment gateway integration
- Worker commission calculation and settlement
- Booking address, schedule, cancellation and notifications
- Ratings/reviews, support and dispute handling
- Privacy policy, terms, account deletion and support contact
- Full Firestore rules review, backend tests and device testing
- Signed release AAB and Play Store listing

**Do not collect real payments or publish publicly** until the payment, admin, security and legal flows have been implemented and tested.

## Firebase setup
1. Open Firebase Console and select project `feroj-service`.
2. Confirm Android app package name is exactly `feroj.service`.
3. Enable Authentication > Email/Password.
4. Create a Cloud Firestore database.
5. Publish `firebase/firestore.rules` in Firestore Rules.
6. Review authorized domains and app configuration before launch.

The supplied `app/google-services.json` identifies project `feroj-service` and package `feroj.service`.

## Build a test APK using GitHub Actions
This project includes `.github/workflows/android-debug-apk.yml`.

1. Create a new **private** repository on GitHub.
2. Upload the contents of this project folder (`FerojLocalService`) to the repository root. Do not upload the outer ZIP folder.
3. Open the repository's **Actions** tab and enable Actions if GitHub asks.
4. Select **Build Android debug APK** and press **Run workflow** (or push to `main`).
5. Wait for the workflow to finish successfully.
6. Open the completed workflow run, find **Artifacts**, and download `firoj-local-service-debug-apk`.
7. Extract the downloaded artifact. It contains `app-debug.apk`, which can be installed for testing on an Android phone.

If the workflow fails, share the complete error log (especially the first Gradle/Kotlin error) so the project can be corrected.

## Build locally
Requirements: Android Studio, JDK 17, Android SDK 35, and Gradle 8.9-compatible tooling. Open this folder in Android Studio, sync Gradle, then choose **Build > Build APK(s)**.

## Release
A debug APK is only for testing. A Play Store release requires a signed Android App Bundle (AAB), a securely stored release keystore, completed production features, a privacy policy, and testing.
