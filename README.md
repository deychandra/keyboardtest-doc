# KeyboardTest.tech — Enterprise Browser-Based Keyboard Diagnostic Suite

[![Documentation Status](https://img.shields.io/badge/docs-latest-brightgreen.svg?style=for-the-badge&logo=markdown)](https://keyboardtest.tech)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)
[![Platform Compatibility](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux%20%7C%20ChromeOS-informational.svg?style=for-the-badge&logo=linux)](SUPPORTED_DEVICES.md)
[![Browser Compatibility](https://img.shields.io/badge/Browsers-Chrome%20%7C%20Firefox%20%7C%20Edge%20%7C%20Safari-orange.svg?style=for-the-badge&logo=googlechrome)](SUPPORTED_BROWSERS.md)
[![Security Policy](https://img.shields.io/badge/Security-Zero--Keylogging-success.svg?style=for-the-badge&logo=shield)](SECURITY.md)

> **KeyboardTest.tech** is the premier, browser-based online keyboard testing and hardware diagnostic utility designed for gamers, mechanical keyboard enthusiasts, software developers, IT administrators, quality control engineers, and laptop users worldwide. Verify key press detection, analyze matrix ghosting, evaluate N-Key Rollover (NKRO), measure hardware polling latency, and detect stuck switches—100% free with zero installation or telemetry.

---

## 🌐 Live Application & Quick Access

[![Launch KeyboardTest.tech](https://img.shields.io/badge/🚀_LAUNCH_LIVE_TEST-KeyboardTest.tech-8A2BE2?style=for-the-badge&logo=rocket)](https://keyboardtest.tech)

- **Official Web Application:** [https://keyboardtest.tech](https://keyboardtest.tech)
- **Documentation Hub:** [docs/index.md](docs/index.md)
- **100-Question FAQ Repository:** [docs/faq.md](docs/faq.md)
- **Report an Issue:** [.github/ISSUE_TEMPLATE/bug_report.md](.github/ISSUE_TEMPLATE/bug_report.md)

---

## 🎯 Executive Summary & Value Proposition

In modern digital workflows, competitive gaming, and software development, input hardware reliability is non-negotiable. A single malfunctioning key switch, an unrecorded modifier keystroke during combo inputs, or subtle key chatter (double-typing) can ruin a competitive match, introduce syntax errors in code, or cause lost productivity.

**KeyboardTest.tech** provides an instant, zero-friction solution for diagnostic validation:

1. **Instant Web Execution:** No `.exe` installers, no browser extensions, no admin permissions needed. Simply open the URL and start pressing keys.
2. **Sub-Millisecond Event Precision:** Leverages native W3C `KeyboardEvent` APIs and `performance.now()` microsecond timers for accurate event capture.
3. **100% Privacy & Zero Keystroke Storage:** Your keystrokes remain strictly inside your browser's client-side RAM. No keystroke data is ever recorded, logged, or transmitted across the network.
4. **Universal Multi-Platform Support:** Works seamlessly across Microsoft Windows, Apple macOS, Linux distributions, and Google ChromeOS.
5. **Adaptive Hardware Visual Matrix:** Real-time visual virtual keyboard matrix automatically renders full-size 100%, TKL 80%, 75%, 65%, 60%, ISO, ANSI, and Mac layouts.

---

## ⚡ Main Technical Features

```
┌──────────────────────────────────────────────────────────────────────────────────┐
│                            KeyboardTest.tech Feature Architecture                 │
├──────────────────┬──────────────────┬──────────────────┬─────────────────────────┤
│  Key Press Test  │  Ghosting Test   │  NKRO Rollover   │  Latency Diagnostics    │
│  Visual Matrix   │  Matrix Phantom  │  Unlimited Keys  │  Sub-ms Frame Timing    │
├──────────────────┼──────────────────┼──────────────────┼─────────────────────────┤
│ Stuck Key Detect │ Multi-Key Combo  │ WebHID Support   │ Cross-Platform Layouts  │
│ Contact Chatter  │ WASD Gaming Test │ Raw Input Code   │ Zero Server Telemetry   │
└──────────────────┴──────────────────┴──────────────────┴─────────────────────────┘
```

### 1. Keystroke Press & Release Detection
- **Visual Key Matrix:** Instant color-coded feedback for every key on standard 104-key ANSI, 105-key ISO, TKL, and laptop keyboards.
- **Key State Color Coding:**
  - **Unpressed (Default):** Neutral state awaiting hardware signal.
  - **Active (Cyan / Blue):** Key is currently depressed physically.
  - **Tested (Green):** Key press and physical release were successfully verified.
  - **Stuck / Chatter (Red):** Key switch fails to send release event or generates chatter rebound signals.
- **Detailed Key Data Inspector:** Displays raw `event.code`, `event.key`, `event.location`, `event.which`, and `keyCode` data in real time.

### 2. Keyboard Ghosting & Anti-Ghosting Matrix Testing
- **Electrical Matrix Ghosting:** Identifies shared circuit column/row trace limitations in budget membrane keyboards where simultaneous multi-key presses fail or produce unintended phantom inputs.
- **Dedicated Gaming Combo Tests:** Specifically engineered tests for critical gaming clusters (`WASD + Space + Shift + Ctrl + Numbers`).
- **Interactive Signal Map:** Visually highlights dropped electrical lines on the virtual board interface.

### 3. N-Key Rollover (NKRO) & 6KRO Verification
- **Unlimited Multi-Key Registration:** Measures exact hardware rollover capabilities (from 2KRO office boards up to true hardware NKRO over USB/PS/2).
- **Peak Rollover Counter:** Real-time counter tracks maximum simultaneous key registrations achieved during testing sessions.

### 4. Hardware Input Latency & Polling Rate Diagnostics
- **High-Precision Timing Engine:** Uses `performance.now()` to measure time intervals between keydown and keyup down to 0.005ms accuracy.
- **High-Frequency USB Polling Rate Support:** Diagnoses high polling rate gaming keyboards (1000Hz, 4000Hz, and 8000Hz Razer/Corsair boards).
- **Debounce & Switch Chatter Analyzer:** Detects switch contact rebound chatter causing accidental double-character inputs (`e.g., ttestingg`).

### 5. Multi-Layout & OS Compatibility Layer
- **Layout Toggles:** One-click switching between ANSI (US), ISO (UK/European), and Apple Mac layouts.
- **Special Key Handling:** Full capturing for PrintScreen, ScrollLock, Pause/Break, NumLock, Windows Key / Super Key, and macOS Command / Option keys.

---

## 🖼️ User Interface & Visual Preview

![KeyboardTest.tech Interface Banner](images/banner.png)

### Layout Matrix & Key State Visualizer
```
[ Esc ]  [ F1 ][ F2 ][ F3 ][ F4 ]  [ F5 ][ F6 ][ F7 ][ F8 ]  [ F9 ][F10][F11][F12]  [PrtSc][ScrLk][Pause]

[ `~ ] [1!][2@][3#][4$][5%][6^][7&][8*][9(][0)][-_][=+] [ Backspace ]  [Insert][Home][PgUp]
[ Tab ]  [Q] [W] [E] [R] [T] [Y] [U] [I] [O] [P] [{}] [}] [  \|  ]  [ Delete ][ End ][PgDn]
[ Caps ]  [A] [S] [D] [F] [G] [H] [J] [K] [L] [;: ] ['" ]  [ Enter ]
[ Shift ]   [Z] [X] [C] [V] [B] [N] [M] [,<] [.>] [/?]   [ Shift ]            [ Up ]
[ Ctrl ][ Win ][ Alt ]   [     Spacebar     ]   [ Alt ][ Win ][ Menu ][ Ctrl ]  [Left][Down][Right]
```

*(Place screenshot images inside `images/screenshots/` directory for local offline visualization).*

---

## 🏆 Why Choose KeyboardTest.tech?

Compared to outdated desktop executables or ad-bloated legacy test websites, KeyboardTest.tech is purpose-built for modern hardware performance and absolute user privacy:

| Feature Comparison | Legacy Desktop Apps | Ad-Heavy Test Sites | KeyboardTest.tech |
| ------------------ | ------------------- | ------------------- | ----------------- |
| **No Software Download Required** | :x: Download Required | :white_check_mark: Browser | :white_check_mark: 100% Zero-Install |
| **Privacy / Zero Keystroke Logging** | :warning: Varies | :x: Ad Tracking Trackers | :white_check_mark: 100% Zero Telemetry |
| **Sub-Millisecond Polling Latency** | :white_check_mark: Native | :x: Slow JS Timers | :white_check_mark: Microsecond `performance.now()` |
| **High Refresh Rate 240Hz+ UI** | :x: Fixed 60Hz UI | :x: Heavy DOM Reflows | :white_check_mark: `requestAnimationFrame` GPU Accelerated |
| **Cross-Platform (Windows/Mac/Linux/ChromeOS)** | :x: Windows Only | :white_check_mark: Partial | :white_check_mark: Full Native Mapping |
| **100% Free Forever** | :x: Paid Shareware | :white_check_mark: Free with Ads | :white_check_mark: Free & Ad-Free Privacy Focus |

---

## 🖥️ Supported Devices & Operating Systems

KeyboardTest.tech works out-of-the-box on any hardware with a physical or wireless keyboard interface:

- **Desktop Keyboards:** Custom mechanical keyboards, full-size membrane office keyboards, Topre boards, Hall Effect magnetic switch boards (Wooting, SteelSeries Apex Pro).
- **Laptops:** Apple MacBook (M1/M2/M3/M4 Apple Silicon & Intel), Lenovo ThinkPad, Dell XPS, HP Spectre, ASUS ROG, Acer, Razer Blade.
- **Operating Systems:**
  - **Microsoft Windows:** 11, 10, 8.1, 7.
  - **Apple macOS:** Sequoia, Sonoma, Ventura, Monterey.
  - **Linux:** Ubuntu, Arch Linux, Fedora, Debian, Linux Mint (Wayland & X11).
  - **Google ChromeOS:** All Chromebook and Chromebox models.

For exhaustive device specifications, see [SUPPORTED_DEVICES.md](SUPPORTED_DEVICES.md).

---

## 🌐 Supported Browsers & Web Engine Compatibility

| Web Browser Engine | Minimum Version | Status | Hardware Acceleration |
| ------------------ | --------------- | ------ | --------------------- |
| **Google Chrome (Blink)** | Version 60+ | :white_check_mark: Fully Supported | Recommended |
| **Mozilla Firefox (Gecko)** | Version 65+ | :white_check_mark: Fully Supported | Recommended |
| **Microsoft Edge (Blink)** | Version 79+ | :white_check_mark: Fully Supported | Recommended |
| **Apple Safari (WebKit)** | Version 12+ | :white_check_mark: Fully Supported | Recommended |
| **Opera & Brave** | Chromium Core | :white_check_mark: Fully Supported | Recommended |

For technical browser API specs, see [SUPPORTED_BROWSERS.md](SUPPORTED_BROWSERS.md).

---

## 📖 Complete Documentation Index

Explore our comprehensive technical guides located in the `docs/` directory:

- 🎬 **[Getting Started Guide](docs/getting-started.md):** Quickstart tutorial for rapid 30-second keyboard diagnostics.
- ⌨️ **[Keyboard Test Guide](docs/keyboard-test.md):** Deep dive into key detection, virtual matrix colors, and layout switching.
- 👻 **[Ghosting Test Guide](docs/ghosting-test.md):** Detailed guide on matrix ghosting, signal pathways, and phantom keypresses.
- 🛡️ **[Anti-Ghosting Hardware Guide](docs/anti-ghosting.md):** PCB circuit engineering, diode placement, and matrix scanning.
- 🔄 **[N-Key Rollover (NKRO) Guide](docs/nkro.md):** USB HID report descriptors, 6KRO limits, PS/2 protocols, and hardware testing.
- ⏱️ **[Keyboard Latency & Polling Guide](docs/keyboard-latency.md):** Measuring polling rates (125Hz to 8000Hz), input lag, and switch debouncing.
- ⚙️ **[How It Works (Under the Hood)](docs/how-it-works.md):** HTML5 `KeyboardEvent` APIs, event.code vs event.key, DOM event bubbling.
- 🎮 **[Gaming Keyboard Guide](docs/gaming-guide.md):** Optimizing WASD clusters, Hall Effect Rapid Trigger switches, and polling rates.
- 🛠️ **[Mechanical Keyboard Guide](docs/mechanical-keyboards.md):** Switch types (Linear/Tactile/Clicky/Magnetic), PCB trace diagnostics, hot-swap troubleshooting.
- 🔧 **[Troubleshooting Guide](docs/troubleshooting.md):** Complete diagnostic tree for stuck keys, double typing, liquid spill repair, and OS remappings.
- ❓ **[100-Question Master FAQ Repository](docs/faq.md):** Comprehensive answers to every keyboard question.

---

## ❓ Frequently Asked Questions (FAQ Overview)

### Q1: Is KeyboardTest.tech safe to use for testing passwords or sensitive keys?
**Yes.** KeyboardTest.tech processes all key presses strictly within your browser's temporary local RAM. Keystrokes are never logged, recorded, or transmitted to any server. However, as a standard security best practice, we recommend not typing sensitive passwords into any active browser tab.

### Q2: Why is my browser not registering the `PrintScreen` or `F11` key?
Certain operating systems or browser shortcuts capture specific function keys before they reach the web page DOM. For example, `F11` triggers browser full-screen mode, and `PrintScreen` may trigger Windows Snipping Tool. Our [Keyboard Test Guide](docs/keyboard-test.md) provides workaround instructions.

### Q3: What is the difference between membrane and mechanical anti-ghosting?
Membrane keyboards share electrical traces across key clusters, leading to ghosting when 3+ keys are pressed together. Mechanical keyboards assign individual switches (often paired with anti-ghosting diodes) to prevent signal bleed, enabling full NKRO.

For 97 additional questions and detailed technical answers, visit [FAQ.md](FAQ.md) or [docs/faq.md](docs/faq.md).

---

## 🤝 Contributing to Documentation

We welcome contributions from technical writers, hardware engineers, mechanical keyboard builders, and open-source enthusiasts!

Please read our **[Contribution Guidelines](CONTRIBUTING.md)** and **[Code of Conduct](CODE_OF_CONDUCT.md)** before submitting pull requests.

```bash
# 1. Fork and clone the documentation repository
git clone https://github.com/keyboardtest/keyboardtest-docs.git
cd keyboardtest-docs

# 2. Create a feature or documentation branch
git checkout -b docs/add-magnetic-switch-guide

# 3. Commit your edits adhering to our SEO frontmatter guidelines
git commit -m "docs: add detailed magnetic switch rapid trigger guide"

# 4. Push to your fork and submit a Pull Request
git push origin docs/add-magnetic-switch-guide
```

---

## 🔒 Security & Vulnerability Policy

Security and privacy are engineered into our client-side architecture by design. If you discover a vulnerability or security concern, please review our [Security Policy](SECURITY.md) and report it to `security@keyboardtest.tech`.

---

## 📜 License

This documentation repository and all associated Markdown files are licensed under the **[MIT License](LICENSE)**.

```
Copyright (c) 2026 KeyboardTest.tech
```

---

## 📬 Contact & Support

- **Website:** [https://keyboardtest.tech](https://keyboardtest.tech)
- **General Inquiries:** `support@keyboardtest.tech`
- **Security Team:** `security@keyboardtest.tech`
- **Privacy Officer:** `privacy@keyboardtest.tech`
- **GitHub Repository Issues:** [Report Issue](.github/ISSUE_TEMPLATE/bug_report.md)
