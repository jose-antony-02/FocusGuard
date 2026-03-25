# FocusGuard
<div align="center">

**Take Back Control of Your Time**

[![Android](https://img.shields.io/badge/Android-7.0+-green.svg)](https://developer.android.com)
[![Kotlin](https://img.shields.io/badge/Kotlin-1.9.22-purple.svg)](https://kotlinlang.org)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

</div>

## 📱 About FocusGuard

FocusGuard is a powerful anti-addiction app that helps you break free from smartphone addiction by blocking distracting apps during focused periods. Unlike basic screen time apps that can be easily bypassed, FocusGuard enforces strict blocking with no loopholes.

## ✨ Features

### Core Blocking
- **Custom App Selection** - Choose exactly which apps to block (Instagram, Chrome, Games, etc.)
- **Daily Schedule** - Set a reset time that automatically blocks apps daily
- **Quick Focus Sessions** - 15/25/60 minute Pomodoro-style focus periods
- **Emergency Override** - 60-second waiting penalty before temporary access

### Smart Features
- **Whitelist Protection** - Camera and Phone apps are always accessible
- **Usage Statistics** - Track blocked attempts and time saved with beautiful charts
- **Notification Reminders** - Get warned 10 minutes before blocking starts
- **Home Screen Widget** - Quick toggle to start focus mode

### Technical Excellence
- **Dual Detection System** - Works on Android 7.0 through Android 15+
- **Accessibility Service** - Reliable app detection on modern Android versions
- **Device Admin** - System-level enforcement that can't be bypassed
- **Foreground Service** - Continuous protection even when app is closed

## 📋 Requirements

- **Android Version**: 7.0 (API 24) and above
- **Storage**: ~6 MB for the app
- **Permissions Required**:
  - Device Admin (for blocking apps)
  - Accessibility Service (for app detection on Android 10+)
  - Usage Access (for statistics tracking)

## 🚀 Installation

### Option 1: Direct Install (Recommended)
1. Download the latest APK from [Releases](https://github.com/YOUR_USERNAME/FocusGuard/releases)
2. Enable "Install from unknown sources" in Settings
3. Open the APK file and tap "Install"
4. Grant permissions when prompted

### Option 2: ADB Install
```bash
adb install app-debug.apk
