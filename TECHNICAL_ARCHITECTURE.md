@"
# FocusGuard - Technical Architecture

## 📋 Overview

FocusGuard is an Android anti-addiction app that blocks distracting apps using system-level permissions. This document explains the architecture, decision-making process, and how each component works.

## 🏗️ High-Level Architecture

┌─────────────────────────────────────────────────────────────────┐
│ FocusGuard App │
├─────────────────────────────────────────────────────────────────┤
│ │
│ ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐ │
│ │ UI Layer │ │ Service Layer │ │ Data Layer │ │
│ │ │ │ │ │ │ │
│ │ • MainActivity │ │ • Accessibility│ │ • Room Database │ │
│ │ • AppSelection │ │ Service │ │ • SharedPrefs │ │
│ │ • Statistics │ │ • Monitor │ │ │ │
│ │ • Widget │ │ Service │ │ │ │
│ └────────┬────────┘ └────────┬───────┘ └────────┬────────┘ │
│ │ │ │ │
│ └────────────────────┼────────────────────┘ │
│ │ │
│ ┌───────────▼───────────┐ │
│ │ Android System │ │
│ │ • Device Admin │ │
│ │ • Accessibility API │ │
│ │ • UsageStats API │ │
│ └───────────────────────┘ │
└─────────────────────────────────────────────────────────────────┘


## 🧩 Component Breakdown

### 1. UI Layer (Activities & Widget)

| Component | File | Responsibility |
|-----------|------|----------------|
| **MainActivity** | `MainActivity.kt` | Dashboard, time picker, permission checks |
| **AppSelectionActivity** | `AppSelectionActivity.kt` | Multi-select app chooser with search |
| **StatsActivity** | `StatsActivity.kt` | Statistics with MPAndroidChart |
| **SessionActivity** | `SessionActivity.kt` | Focus timer with countdown |
| **EmergencyOverrideActivity** | `EmergencyOverrideActivity.kt` | 60-second wait penalty screen |
| **BlockActivity** | `BlockActivity.kt` | Block screen shown when app is blocked |
| **FocusWidget** | `FocusWidget.kt` | Home screen quick toggle widget |

### 2. Service Layer (Background Processing)

#### AccessibilityService - `FocusGuardAccessibilityService.kt`

**Purpose:** Detects when apps are opened (critical for Android 10+)

```kotlin
How it works:
1. Android system sends events to Accessibility Service
2. Service listens for TYPE_WINDOW_STATE_CHANGED events
3. Extracts package name of the app being opened
4. Checks if app is blocked and focus mode is active
5. If yes → launches BlockActivity
6. Returns user to home screen
