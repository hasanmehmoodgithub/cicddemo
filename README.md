# cididemo

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

## Android CI/CD (GitHub Actions)

This project includes an Android pipeline at `.github/workflows/android-build.yml`.

- On pull requests, it runs tests and builds a debug APK.
- On pushes to `main`/`master` (or manual run), it runs tests and builds:
  - release APK
  - release AAB
- Build outputs are uploaded as workflow artifacts.

### Optional release signing setup

If signing secrets are available, release artifacts are signed in CI. Without secrets, CI still builds using fallback debug signing.

Add these repository secrets in GitHub:

- `ANDROID_KEYSTORE_BASE64`: base64 of your `.jks` keystore file
- `ANDROID_STORE_PASSWORD`
- `ANDROID_KEY_PASSWORD`
- `ANDROID_KEY_ALIAS`

Example command to create `ANDROID_KEYSTORE_BASE64`:

```bash
base64 -i android/upload-keystore.jks | pbcopy
```
