<!--
SEO Title: Getting Started with KeyboardTest.tech | Quickstart Guide
Meta Description: Learn how to test your keyboard in under 30 seconds with KeyboardTest.tech. Step-by-step tutorial for keypress verification, layout selection, and troubleshooting.
Primary Keyword: how to test keyboard online
Secondary Keywords: keyboard testing quickstart, test keyboard keys, keyboard test tutorial, online key tester guide
URL Slug: docs/getting-started.md
Suggested Internal Links: docs/index.md, docs/keyboard-test.md, docs/ghosting-test.md, docs/troubleshooting.md, docs/faq.md
External Reference Suggestions: W3C DOM Level 3 Events Specification (w3.org)
-->

# Getting Started with KeyboardTest.tech

Welcome to the **KeyboardTest.tech Quickstart Guide**. Whether you have just unpacked a brand new custom mechanical keyboard, suspect a broken switch on your laptop, or want to verify anti-ghosting performance for competitive gaming, this tutorial will guide you through testing your hardware in under 30 seconds.

---

## 📋 Overview

**KeyboardTest.tech** is a zero-installation web application that captures hardware keypresses directly through your web browser. When you press a physical key on your keyboard, your computer transmits an electrical scan code to your operating system, which passes a `KeyboardEvent` to the web browser. KeyboardTest.tech intercepts these events instantly and updates a visual interactive keyboard layout matrix in real time.

---

## 🎯 Purpose & Benefits

### Why Perform a Quickstart Keyboard Test?
- **Immediate Diagnostic Verification:** Confirm that every key on your keyboard is firing its expected signal upon arrival or after cleaning.
- **Isolate Hardware vs. Software Issues:** Quickly determine whether an unresponsive key is caused by physical switch failure or a software bug in a specific desktop app.
- **Zero Software Overhead:** Avoid installing bloated third-party executable software or vendor drivers just to perform basic hardware sanity checks.
- **Complete Privacy Protection:** Guarantee that zero typing data or keystrokes leave your machine during diagnostics.

---

## 🔬 How It Works: The 3-Step Execution Model

```
 ┌────────────────────────┐      ┌────────────────────────┐      ┌────────────────────────┐
 │  1. Physical Actuation │ ───► │ 2. Browser Event Intercept │ ───► │ 3. Real-Time UI Render │
 │ User presses key switch│      │ JS listens to keydown  │      │ Matrix highlights key  │
 └────────────────────────┘      └────────────────────────┘      └────────────────────────┘
```

1. **Physical Actuation:** Depressing a key switch bridges the electrical circuit on your keyboard's Printed Circuit Board (PCB).
2. **Browser Event Interception:** The operating system passes the hardware scancode to your web browser. KeyboardTest.tech captures the standard W3C `KeyboardEvent.code` property.
3. **Real-Time UI Rendering:** The corresponding visual key cap on the interactive canvas/DOM lights up instantly, tracking press, release, and active states.

---

## 🚀 Step-by-Step Testing Guide

### Step 1: Open the Application
Navigate to **[https://keyboardtest.tech](https://keyboardtest.tech)** in any modern web browser (Google Chrome, Mozilla Firefox, Microsoft Edge, or Apple Safari).

### Step 2: Select Your Physical Keyboard Layout
By default, KeyboardTest.tech loads the standard **104-key ANSI (US)** layout. If your physical keyboard uses a different layout:
1. Locate the **Layout Selector** dropdown above the virtual keyboard interface.
2. Choose your layout:
   - **ANSI (US):** Standard rectangular Enter key, wide left Shift.
   - **ISO (UK / European):** Tall L-shaped Enter key, split left Shift with extra backslash key.
   - **Apple Mac Layout:** Includes Command (`⌘`), Option (`⌥`), and Mac function key arrangements.
   - **Compact Layouts (TKL / 75% / 65% / 60%):** Select compact view filters to remove unused keys.

### Step 3: Begin Pressing Keys
Press every physical key on your keyboard one at a time, moving sequentially from left to right across each row:
- Start with the top Escape and Function key row (`Esc`, `F1` through `F12`).
- Proceed through the number row, QWERTY row, ASDF row, and ZXCV row.
- Test modifier keys (`Ctrl`, `Alt`, `Shift`, `Windows / Command`).
- Test navigation keys (`Arrow keys`, `Insert`, `Delete`, `Home`, `End`, `PageUp`, `PageDown`).
- Test the Numpad cluster if present on full-size boards.

### Step 4: Interpret the Visual Key Colors

| Key Visual State | Color Indicator | Meaning & Diagnostic Status |
| ---------------- | --------------- | --------------------------- |
| **Untested** | Dark Gray / Neutral | Key has not been pressed yet during this session. |
| **Active** | Bright Cyan / Blue | Key is currently being depressed physically. |
| **Tested** | Vivid Green | Key was successfully pressed and released. Switch is functioning properly. |
| **Stuck / Error** | Pulsing Red | Key sent a press event but failed to register a physical release event (indicates stuck switch mechanism or liquid damage). |

### Step 5: Inspect the Real-Time Key Inspector Data
Look at the **Live Key Data Inspector** box below the virtual keyboard matrix. When you press any key, it displays:
- **`Key Code` (`event.code`):** Physical location code (e.g., `KeyA`, `Space`, `Enter`).
- **`Key Value` (`event.key`):** Value generated (e.g., `"a"`, `"A"`, `"Enter"`).
- **`Location` (`event.location`):** Standard (`0`), Left (`1`), Right (`2`), Numpad (`3`).
- **`Press Duration`:** Time in milliseconds that the key was held down.

---

## 💡 Expert Testing Tips

1. **Test Modifier Pairs Separately:** Always test both Left Shift and Right Shift, Left Ctrl and Right Ctrl, Left Alt and Right Alt. They possess separate hardware scan codes.
2. **Check Lock Key LEDs:** When testing `Caps Lock`, `Num Lock`, and `Scroll Lock`, verify that both the visual matrix key turns green AND your physical keyboard LED light turns on/off.
3. **Use Full-Screen Mode for Testing:** Press `F11` (or `Cmd + Ctrl + F` on Mac) to enter full-screen mode, preventing accidental tab switching when pressing complex key combinations.

---

## ⚠️ Common Mistakes to Avoid

- **Mistake 1: Typing While Browser Tab is Out of Focus.**  
  *Solution:* Ensure you click inside the KeyboardTest.tech browser window so it has active DOM input focus. If you click another application window, keystrokes will not reach the test matrix.
- **Mistake 2: Confusing Language Layouts with Physical Key Codes.**  
  *Solution:* KeyboardTest.tech tracks physical location via `event.code`. If your OS input language is set to German (QWERTZ) or French (AZERTY), the letter produced may differ, but the physical key box tested will match your physical key position.
- **Mistake 3: Forgetting Third-Party Extension Interceptions.**  
  *Solution:* Browser extensions like Vimium, password managers, or screen recorders may capture `Tab` or `Esc` keys. Disable intercepting extensions or use an Incognito / Private window.

---

## ❓ Frequently Asked Questions

### Q1: Why did my `PrintScreen` key not turn green?
On Microsoft Windows, the `PrintScreen` key may trigger the system Snipping Tool or OS screen capture snippet before the browser receives the release event. Try holding `Fn + PrintScreen` or `Alt + PrintScreen`.

### Q2: Can I test my mouse or touchpad on this page?
KeyboardTest.tech is specialized for keyboard diagnostics. For mouse testing, use dedicated click and scroll diagnostics tools.

### Q3: How do I reset the test board to start over?
Click the bright **"Reset Board"** button above the virtual matrix to clear all highlighted green and red keys.

---

## 🔗 Related Documentation & Internal Links

- [Documentation Portal Home](index.md)
- [In-Depth Keyboard Test Guide](keyboard-test.md)
- [Keyboard Ghosting & Multi-Key Guide](ghosting-test.md)
- [Hardware Troubleshooting Tree](troubleshooting.md)
- [Master 100-Question FAQ Repository](faq.md)
