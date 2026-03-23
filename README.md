## Anti-Addiction App for Android

FocusGuard helps you break phone addiction by blocking distracting apps during focus times.

## Features

- ✅ Custom app blocking (choose which apps to block)
- ✅ Daily reset time scheduling
- ✅ Quick focus sessions (25 min Pomodoro-style)
- ✅ Emergency override with 60-second penalty
- ✅ Statistics dashboard with charts
- ✅ Home screen widget
- ✅ Android 15 compatibility (uses Accessibility Service)

## Permissions Required

- **Device Admin**: Required to block apps at system level
- **Accessibility Service**: Required for Android 15 app detection
- **Usage Stats**: For tracking blocked attempts

## Building the App

\`\`\`bash
.\gradlew clean
.\gradlew assembleDebug
\`\`\`

## Installation

\`\`\`bash
adb install app/build/outputs/apk/debug/app-debug.apk
\`\`\`

## Tech Stack

- Kotlin
- Android SDK 35 (Android)
- Room Database
- MPAndroidChart
- Coroutines

## Status

✅ Working on Android with Accessibility Service support

## License

MIT
" > README.md

# Add and commit README
git add README.md
git commit -m "Add README documentation"
git push
