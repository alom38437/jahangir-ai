# Jahangir AI — Web App + Android project

## Web app
- Open `web/index.html` in a browser for a basic local test (live API requires internet).
- For installable PWA, host the entire `web/` folder on an HTTPS static host (for example GitHub Pages or Netlify), then open the HTTPS URL in Android Chrome and choose **Install app** / **Add to Home screen**.
- The app polls Delta Exchange India public BTCUSD ticker every 5 seconds.
- No API key, Telegram token, or trading permission is used.

## Android APK project
The `android/` folder is an Android Studio project using a WebView that loads the bundled web app offline and fetches live data when online.
To build an APK:
1. Open `android/` in Android Studio.
2. Let Gradle sync and install the Android SDK if prompted.
3. Select Build > Build Bundle(s) / APK(s) > Build APK(s).
4. Android Studio shows the APK location, usually `app/build/outputs/apk/debug/app-debug.apk`.

This package contains Android project source, not a precompiled APK. A precompiled APK needs an Android SDK/build environment and signing/build step.

## Signal and accuracy notes
- UP/DOWN are experimental momentum labels, not trained AI predictions.
- Signal is based on ticker samples near 30s and 10s lookbacks.
- A directional call is evaluated after 30 seconds against its entry ticker price.
- Accuracy excludes WAIT and flat outcomes. Fees, spread, slippage and execution are not modeled.
- Do not use the displayed percentage as proof of profitability. Paper-test first.
