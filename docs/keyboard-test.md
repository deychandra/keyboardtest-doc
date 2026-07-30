<!--
SEO Title: Online Keyboard Key Press Test Guide | KeyboardTest.tech
Meta Description: Learn how to test every key on your keyboard with KeyboardTest.tech. Detailed guide covering key press detection, stuck keys, matrix visualizer, and layout mapping.
Primary Keyword: online keyboard test
Secondary Keywords: test keyboard keys, keyboard press detector, stuck key detector, keyboard layout tester, key check online
URL Slug: docs/keyboard-test.md
Suggested Internal Links: docs/getting-started.md, docs/ghosting-test.md, docs/mechanical-keyboards.md, docs/troubleshooting.md, docs/faq.md
External Reference Suggestions: W3C UI Events KeyboardEvent Code Values (w3.org)
-->

# Comprehensive Keyboard Key Press Test Guide

Welcome to the definitive guide on conducting a complete key press detection audit using **KeyboardTest.tech**. This manual explains the mechanics of keypress registration, visual matrix state colors, stuck key detection, layout customization, and diagnostic interpretation.

---

## 📋 Overview

The **Keyboard Test** is the core diagnostic module of KeyboardTest.tech. It provides a real-time, interactive virtual representation of your physical keyboard. As you actuate physical keys on your keyboard, the application captures raw input signals from the operating system and updates the corresponding keys on the screen.

Whether you are testing an office membrane board, a high-end custom mechanical keyboard, or a laptop keyboard after liquid exposure, the Keyboard Test provides immediate, unambiguous confirmation of hardware integrity.

---

## 🎯 Purpose & Key Benefits

```
 ┌─────────────────────────────────────────────────────────────────────────────┐
 │                         Keyboard Test Value Architecture                    │
 ├───────────────────────┬─────────────────────────┬───────────────────────────┤
 │ 1. Hardware Verification│ 2. Stuck Key Isolation  │ 3. Layout Accuracy        │
 │ Validates 100% of key │ Identifies failing key  │ Matches physical ANSI,    │
 │ switches & PCB traces │ contact points & chatter│ ISO, and Mac keyboards    │
 └───────────────────────┴─────────────────────────┴───────────────────────────┘
```

1. **Complete Matrix Auditing:** Rapidly audit every single key on 104-key, 87-key TKL, 75%, 65%, 60%, and laptop keyboards.
2. **Stuck Key & Chatter Detection:** Automatically flag keys that fail to send release signals or generate rapid false rebound presses.
3. **Hardware Scancode Inspection:** Inspect exact hardware scancodes (`event.code`) to diagnose remapping issues caused by third-party software like AutoHotkey, SharpKeys, or Karabiner-Elements.
4. **Zero Latency Tracking:** Render keypress highlights synchronously with your monitor's high refresh rate (up to 540Hz) for zero visual lag.

---

## 🔬 Technical Mechanics of Key Press Detection

When you press a physical key on your keyboard:
1. **Actuation:** The switch stem moves downward, causing conductive contact leaves (mechanical) or conductive rubber domes (membrane) to bridge an electrical circuit trace on the Printed Circuit Board (PCB).
2. **Microcontroller Scan:** The keyboard's onboard microcontroller (e.g., ATmega32U4, RP2040, or ARM Cortex chip) scans the matrix grid and generates a binary HID USB Scancode.
3. **OS Dispatch:** The USB HID controller driver in Windows, macOS, or Linux maps the scancode into a virtual key event and dispatches it to the active window application.
4. **DOM Event Capture:** KeyboardTest.tech attaches global JavaScript event listeners to the browser window object:

```typescript
window.addEventListener('keydown', (event: KeyboardEvent) => {
  // Captures physical hardware code (e.g. "KeyA", "Space", "NumpadEnter")
  const code = event.code; 
  updateVirtualKeyUI(code, 'active');
});

window.addEventListener('keyup', (event: KeyboardEvent) => {
  const code = event.code;
  updateVirtualKeyUI(code, 'tested');
});
```

---

## 🎨 Visual Matrix Key State Breakdown

KeyboardTest.tech utilizes a four-tier color visual matrix system:

```
┌──────────────┬──────────────┬──────────────┬──────────────┐
│  Untested    │   Active     │   Tested     │ Stuck / Error│
│  (Dark Gray) │  (Cyan/Blue) │   (Green)    │ (Pulsing Red)│
└──────────────┴──────────────┴──────────────┴──────────────┘
```

### 1. Untested State (Dark Gray / Neutral)
- **Visual:** Neutral background color.
- **Meaning:** Key has not transmitted any input signal during the current diagnostic session.

### 2. Active State (Bright Cyan / Electric Blue)
- **Visual:** High-contrast illuminated cyan highlight.
- **Meaning:** Key switch is currently depressed physically. The browser is receiving an active `keydown` event stream.

### 3. Tested State (Vivid Emerald Green)
- **Visual:** Solid emerald green highlight.
- **Meaning:** Key was successfully depressed and physically released. The system confirmed both `keydown` and `keyup` event integrity.

### 4. Stuck / Error State (Pulsing Crimson Red)
- **Visual:** Flashing crimson red highlight.
- **Meaning:** The key sent a `keydown` event but failed to transmit a `keyup` event within expected parameters, or transmitted rapid intermittent rebound signals without physical release.

---

## 🛠️ Step-by-Step Testing Procedure

### Step 1: Initialize the Test Environment
Open [KeyboardTest.tech/keyboard-test](https://keyboardtest.tech) and verify that the virtual keyboard matches your device's physical layout (ANSI, ISO, or Mac).

### Step 2: Systematically Test Primary Typing Clusters
1. **Alphabetical Cluster:** Press keys `A` through `Z` sequentially.
2. **Number Row:** Press `1` through `0`, including `-` and `=`.
3. **Punctuation & Brackets:** Test `[`, `]`, `\`, `;`, `'`, `,`, `.`, `/`.

### Step 3: Test Function & Navigation Rows
1. **Function Keys:** Press `F1` through `F12`.
2. **System Keys:** Press `Escape`, `PrintScreen`, `ScrollLock`, and `Pause/Break`.
3. **Navigation Block:** Press `Insert`, `Home`, `PageUp`, `Delete`, `End`, `PageDown`, and all four `Arrow Keys`.

### Step 4: Test Modifiers & Special Keys
1. **Modifier Pairs:** Separately test Left Shift, Right Shift, Left Ctrl, Right Ctrl, Left Alt, Right Alt, and Windows / Command key.
2. **Spacebar & Enter:** Press Spacebar, main Enter key, and Numpad Enter key.

### Step 5: Verify Lock Key Status
Press `Caps Lock`, `Num Lock`, and `Scroll Lock`. Verify that both the virtual key lights up and your hardware keyboard status LED responds correctly.

---

## 💡 Pro Tips for Advanced Key Diagnostics

- **Detecting Double Typing (Key Chatter):**  
  Press keys lightly and rapidly. If a single physical press registers two rapid green flashes or causes a character count to increment by two in the inspector box, your switch switch contacts suffer from chatter (debouncing failure).
- **Testing Hot-Swap PCB Sockets:**  
  When building custom mechanical keyboards, test your PCB on KeyboardTest.tech with metal tweezers bridging the switch socket pads *before* inserting switches to verify PCB trace health.
- **Testing Numpad Switches:**  
  If the Numpad keys fail to register, verify that `Num Lock` is enabled. When `Num Lock` is disabled, Numpad keys send navigation events (`Home`, `End`, `Arrow` codes) rather than numeric codes.

---

## ⚠️ Common Pitfalls & Mistakes

1. **System Hotkey Interception:**  
   - Windows key combinations like `Win + L` (Lock Workstation) or `Win + D` (Show Desktop) cause Windows to minimize the browser, missing the `keyup` event.
   - *Fix:* Test the Windows / Super key by tapping it quickly without holding other keys.
2. **Browser Tab Unfocused:**  
   If you switch tabs or open DevTools, browser security prevents background tabs from capturing keystrokes. Keep the test tab focused.
3. **Physical Debris in Switch Mechanism:**  
   Dust, hair, or crumbs trapped inside a mechanical switch housing can prevent full switch travel or cause intermittent contact failure.

---

## ❓ Frequently Asked Questions

### Q1: Why does my Left Shift turn green, but Right Shift remains gray?
Left Shift and Right Shift possess distinct hardware scancodes (`ShiftLeft` vs `ShiftRight`). You must physically press the Right Shift key to test it.

### Q2: What should I do if a key turns bright red during testing?
A red key indicates a stuck key switch or a missing release signal. Try removing the keycap and cleaning around the switch stem with compressed air or 99% isopropyl alcohol.

### Q3: Can KeyboardTest.tech detect key remappings?
Yes. The inspector box displays both the physical location code (`event.code`) and the mapped character (`event.key`), allowing you to instantly see if software like SharpKeys or AutoHotkey altered your key bindings.

---

## 🔗 Related Documentation & Links

- [Documentation Portal Home](index.md)
- [Quickstart Guide](getting-started.md)
- [Ghosting Test Guide](ghosting-test.md)
- [Mechanical Keyboard Diagnostic Guide](mechanical-keyboards.md)
- [Hardware Troubleshooting Tree](troubleshooting.md)
- [Master 100-Question FAQ Repository](faq.md)
