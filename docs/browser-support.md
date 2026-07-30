<!--
SEO Title: Browser Compatibility & Web APIs | KeyboardTest.tech
Meta Description: Comprehensive browser compatibility guide for KeyboardTest.tech. Technical specs for Chrome, Firefox, Edge, Safari, WebHID, and GPU acceleration.
Primary Keyword: browser compatibility keyboard test
Secondary Keywords: web keyboard API support, chrome keyboard event test, firefox keyboard test compatibility, webhid keyboard diagnostic
URL Slug: docs/browser-support.md
Suggested Internal Links: docs/getting-started.md, docs/how-it-works.md, docs/keyboard-latency.md, docs/troubleshooting.md, docs/faq.md
External Reference Suggestions: CanIUse KeyboardEvent API Technical Matrix (caniuse.com)
-->

# Complete Browser Support & Technical Web API Specifications

Welcome to the **Browser Support & Performance Manual** for **KeyboardTest.tech**. To deliver sub-millisecond keypress capture and fluid 240Hz+ virtual matrix animation, KeyboardTest.tech builds upon modern HTML5 Web standards. This document details browser compatibility, Web API support, rendering engine optimizations, and hardware acceleration recommendations.

---

## 📋 Overview

**KeyboardTest.tech** is engineered for 100% cross-browser operation without requiring external plugins or installation packages. It is fully compatible with all major desktop and mobile browser engines: Blink (Google Chrome, Microsoft Edge, Opera, Brave), Gecko (Mozilla Firefox), and WebKit (Apple Safari).

---

## 🎯 Purpose & Key Performance Metrics

```
 ┌─────────────────────────────────────────────────────────────────────────────┐
 │                         Browser Performance Pillars                         │
 ├─────────────────────────┬─────────────────────────┬─────────────────────────┤
 │ 1. Zero Input Delay     │ 2. High-Frame Animation │ 3. Broad Web API Support│
 │ Microsecond event       │ GPU-accelerated canvas  │ KeyboardEvent, WebHID,  │
 │ listener dispatch       │ syncs to 240Hz+ monitors│ performance.now() API   │
 └─────────────────────────┴─────────────────────────┴───────────────────────────┘
```

---

## 📊 Comprehensive Browser Compatibility Matrix

| Web Browser | Engine | Minimum Version | Full Support Version | Key API Capabilities |
| ----------- | ------ | --------------- | -------------------- | -------------------- |
| **Google Chrome** | Blink | Chrome 60+ | Chrome 120+ | `KeyboardEvent.code`, WebHID, High-Res Timers, GPU Accel |
| **Mozilla Firefox** | Gecko | Firefox 65+ | Firefox 122+ | `KeyboardEvent.code`, High-Res Timers, Full Layout Support |
| **Microsoft Edge** | Blink | Edge 79+ | Edge 120+ | `KeyboardEvent.code`, WebHID, High-Res Timers, GPU Accel |
| **Apple Safari** | WebKit | Safari 12+ | Safari 17+ | `KeyboardEvent.code`, High-Res Timers, Mac Key Mapping |
| **Brave Browser** | Blink | All Versions | Latest Release | `KeyboardEvent.code`, WebHID, Privacy Shield Compatible |
| **Opera** | Blink | Opera 50+ | Latest Release | `KeyboardEvent.code`, WebHID, High-Res Timers |
| **Vivaldi** | Blink | Vivaldi 2.0+ | Latest Release | `KeyboardEvent.code`, WebHID, High-Res Timers |

---

## 🔬 Web APIs & Technical Feature Breakdown

### 1. W3C `KeyboardEvent` Standard (Universal Support)
- **Support:** 100% across Chrome, Firefox, Edge, Safari, Opera, Brave.
- **Functionality:** Provides physical scancode abstraction via `event.code` (`KeyA`, `Space`, `Enter`) and logical key values via `event.key`.

### 2. High-Resolution Time API (`performance.now()`)
- **Support:** 100% across all modern browser engines.
- **Functionality:** Returns floating-point timestamps in milliseconds with microsecond precision ($0.005\text{ ms}$), enabling precise measurement of key hold duration and polling intervals.

### 3. WebHID API (Optional Advanced Diagnostics)
- **Support:** Chrome 89+, Edge 89+, Opera 75+ (Not supported in Safari/Firefox due to Apple/Mozilla security policies).
- **Functionality:** Allows web applications to open direct raw USB Human Interface Device endpoints to read unmapped physical key scancodes and write LED status states directly to custom mechanical keyboards.

### 4. Animation Frame API (`window.requestAnimationFrame`)
- **Support:** 100% across all browsers.
- **Functionality:** Synchronizes UI matrix DOM repaints directly with the user's display refresh rate (60Hz, 144Hz, 240Hz, 360Hz, 540Hz), eliminating UI stutter during rapid multi-key rollover testing.

---

## 💡 Recommended Browser Configuration Settings

To ensure maximum testing accuracy and prevent missed inputs:

1. **Enable Hardware Acceleration:**  
   - Chrome / Edge: Navigate to `chrome://settings/system` and toggle **"Use graphics acceleration when available"** to ON.
   - Firefox: Navigate to `about:preferences` -> Performance -> check **"Use recommended performance settings"**.
2. **Disable Shortcut-Intercepting Extensions:**  
   Extensions like *Vimium*, *Tridactyl*, or password managers may trap `Tab`, `Esc`, or `F1`-`F12` keys before they reach the webpage. Test in an Incognito / Private window with extensions disabled.

---

## ❓ Frequently Asked Questions

### Q1: Why does Safari display different key names for Command and Option?
Apple Safari maps `event.code` correctly, but formats `event.key` as `"Meta"` for Command (`⌘`) and `"Alt"` for Option (`⌥`). KeyboardTest.tech normalizes these labels automatically on Mac devices.

### Q2: Is KeyboardTest.tech compatible with mobile browsers on iOS and Android?
Yes, but mobile browsers only generate virtual keyboard events when an external physical Bluetooth keyboard or USB-C OTG keyboard is connected.

---

## 🔗 Related Documentation & Links

- [Documentation Portal Home](index.md)
- [How Keyboard Testing Works](how-it-works.md)
- [Keyboard Latency & Polling Guide](keyboard-latency.md)
- [Troubleshooting & Diagnostic Guide](troubleshooting.md)
- [Master 100-Question FAQ Repository](faq.md)
