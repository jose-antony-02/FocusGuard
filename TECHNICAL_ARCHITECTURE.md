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
