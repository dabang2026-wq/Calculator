# Simple Cord Length Calculator — Android App Project

**Brand:** Developed by จาตูไหม่  
**Application ID:** `com.jatumae.cordlength`

This package contains the latest calculator web app bundled as local assets for a native Android shell using Capacitor. The calculator's existing interface and features are included, including customizable Quick Slack Presets.

## Build an installable Android APK

You need a computer with Node.js (LTS), Android Studio, and an Android SDK installed. This source package does not include a compiled APK because the Android build toolchain is not installed in the packaging environment.

1. Extract this ZIP.
2. Open a terminal in the extracted `cord-mobile-app` folder.
3. Install dependencies:

   ```bash
   npm install
   ```

4. Generate the Android native project:

   ```bash
   npx cap add android
   ```

   If Capacitor says the Android platform already exists, continue to the next step.

5. Sync the bundled app into Android:

   ```bash
   npx cap sync android
   ```

6. Open Android Studio:

   ```bash
   npx cap open android
   ```

7. In Android Studio, wait for Gradle sync. To make a test build, choose **Build > Build Bundle(s) / APK(s) > Build APK(s)**. Android Studio will show the output location when complete.

For a signed release APK, choose **Build > Generate Signed Bundle / APK** and follow Android Studio's signing wizard. Keep the signing key private and backed up.

## Test on a phone

Enable Developer options and USB debugging on your Android device, connect it to the computer, then use Android Studio's Run button. Alternatively, transfer the generated APK to your phone and install it, allowing installs from that source when Android asks.

## Data and offline behavior

The calculator is bundled inside the app, so its interface does not need a hosted website to open. User history and preferences are stored locally by the app's WebView origin and are separate from browser-site storage. Uninstalling the app or clearing its app data may remove those local records. Export or back up important records before doing either.

## Project contents

- `www/index.html` — calculator interface and logic
- `www/manifest.json` — web app metadata
- `www/service-worker.js` — offline shell cache logic
- `capacitor.config.json` — native app ID and display name
- `package.json` — Capacitor dependencies and commands
