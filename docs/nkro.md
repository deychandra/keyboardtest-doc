<!--
SEO Title: N-Key Rollover (NKRO) vs 6KRO Test & Guide | KeyboardTest.tech
Meta Description: Comprehensive N-Key Rollover (NKRO) testing guide. Learn the difference between 6KRO and NKRO, USB HID limits, PS/2 interfaces, and NKRO testing online.
Primary Keyword: nkro test online
Secondary Keywords: n key rollover test, 6kro vs nkro, keyboard rollover test, test nkro online, multi key rollover tester
URL Slug: docs/nkro.md
Suggested Internal Links: docs/getting-started.md, docs/ghosting-test.md, docs/anti-ghosting.md, docs/keyboard-latency.md, docs/gaming-guide.md, docs/faq.md
External Reference Suggestions: USB Implementers Forum Device Class Definition for Human Interface Devices (HID)
-->

# Complete Guide to N-Key Rollover (NKRO) & 6KRO Testing

Welcome to the definitive **N-Key Rollover (NKRO) Technical Manual** on **KeyboardTest.tech**. N-Key Rollover represents the pinnacle of keyboard hardware performance, allowing an unlimited number of simultaneous keypresses to register cleanly. This guide details the mechanics of rollover, USB Human Interface Device (HID) protocol limitations, PS/2 legacy interfaces, and online testing methods.

---

## 📋 Overview

**N-Key Rollover (NKRO)** is a hardware capability where every single key on a keyboard can be pressed simultaneously (`N` standing for the number of keys on the board) without any key failing to register.

In contrast, standard office keyboards operate under **6-Key Rollover (6KRO)** restrictions due to standard USB HID boot protocol specifications, capping simultaneous inputs at 6 alphanumeric keys plus modifier keys.

---

## 🎯 Purpose & Key Benefits

```
 ┌─────────────────────────────────────────────────────────────────────────────┐
 │                         N-Key Rollover (NKRO) Benefits                      │
 ├─────────────────────────┬─────────────────────────┬─────────────────────────┤
 │ 1. Zero Input Dropping  │ 2. Rhythm Game Perfection│ 3. High-Speed Typing   │
 │ Press 20+ keys without  │ Crucial for Osu!,       │ Supports chord-based    │
 │ losing a single input   │ DDR, and IIDX gaming    │ steno & braille typing  │
 └─────────────────────────┴─────────────────────────┴───────────────────────────┘
```

- **Unrestricted Multi-Key Execution:** Essential for rhythm games, fighting games (simultaneous button combinations), and speed typing.
- **Bypass USB Bottlenecks:** Eliminates the 6-key USB protocol barrier through advanced HID report descriptor multiplexing.
- **Hardware Validation:** Verify whether your gaming keyboard's advertised "Full NKRO over USB" claim is genuine.

---

## 🔬 Technical Mechanics: 6KRO vs. True NKRO

### 1. The USB HID 8-Byte Report Buffer Limit (6KRO)
The original USB Human Interface Device (HID) specification established a standard 8-byte report buffer transmitted from the keyboard controller to the host OS on every polling cycle:

```
┌──────────┬──────────┬──────────┬──────────┬──────────┬──────────┬──────────┬──────────┐
│ Byte 0   │ Byte 1   │ Byte 2   │ Byte 3   │ Byte 4   │ Byte 5   │ Byte 6   │ Byte 7   │
│ Modifiers│ Reserved │ Key 1    │ Key 2    │ Key 3    │ Key 4    │ Key 5    │ Key 6    │
└──────────┴──────────┴──────────┴──────────┴──────────┴──────────┴──────────┴──────────┘
```

- **Byte 0:** Bitfield tracking up to 8 modifier keys (`L-Ctrl`, `L-Shift`, `L-Alt`, `L-Win`, `R-Ctrl`, `R-Shift`, `R-Alt`, `R-Win`).
- **Byte 1:** Reserved byte (OEM use).
- **Bytes 2–7:** Exactly 6 data slots for standard key usage codes.
- **The Limit:** If you press 7 standard alphanumeric keys simultaneously (e.g., `A S D F G H J`), the 7th key code cannot fit inside the 8-byte USB packet and is dropped!

### 2. How Manufacturers Achieve Full NKRO Over USB
To bypass the 8-byte USB HID bottleneck, modern keyboard firmware (such as QMK, VIA, or custom gaming microcontrollers) employs two clever engineering techniques:

#### Method A: Multi-Interface HID Emulation (Bitmap / Composite HID)
The keyboard presents itself to the operating system as multiple virtual USB HID keyboards simultaneously (or sends a single extended HID report descriptor containing a 128-bit array). Each bit in the 128-bit array represents one physical key on the keyboard ($1 = \text{Pressed}, 0 = \text{Released}$). This allows reporting all 104 keys simultaneously over a single USB connection!

#### Method B: PS/2 Connection Mode
Legacy PS/2 keyboard ports operate using hardware interrupts rather than polled USB buffer packets. PS/2 natively supports true, unbuffered NKRO at the hardware motherboard level.

---

## 📊 Comparative Summary: Rollover Standards

| Rollover Spec | Max Simultaneous Keys | Protocol | Target Use Case |
| ------------- | --------------------- | -------- | --------------- |
| **2KRO** | 2 keys | Basic Matrix | Ultra-budget office keyboards |
| **6KRO** | 6 keys + Modifiers | Standard USB HID | Standard laptops & basic keyboards |
| **10KRO** | 10 keys | Expanded Buffer | Touch-typing & 10-finger testing |
| **Full NKRO** | Unlimited (All 104+ keys) | Composite USB / PS/2 | Mechanical gaming & rhythm games |

---

## 🛠️ Step-by-Step NKRO Testing Guide on KeyboardTest.tech

1. Open **[KeyboardTest.tech/nkro](https://keyboardtest.tech)**.
2. Place both palms flat across your keyboard, depressing as many keys as possible simultaneously (e.g., 15 to 25 keys).
3. Observe the **"Simultaneous Key Counter"** display below the matrix.
4. **Diagnostic Evaluation:**
   - If the counter stops at **6 keys**, your keyboard is restricted to **6KRO**.
   - If the counter reaches **10, 15, 20, or more keys**, your keyboard supports **True NKRO**.

---

## 💡 Pro Tips for NKRO Optimization

- **Toggle Software NKRO Switches:** Some mechanical keyboards feature a physical hotkey shortcut (e.g., `Fn + N` or `Fn + F12`) to toggle between 6KRO (for legacy BIOS compatibility) and NKRO mode.
- **BIOS Compatibility Mode:** Older motherboard BIOS screens may fail to recognize keyboards operating in composite NKRO mode. Switch your keyboard back to 6KRO mode when configuring BIOS setup screens.

---

## ❓ Frequently Asked Questions

### Q1: Do human typists really need NKRO?
Fast touch-typists frequently exceed 120 WPM, leading to key overlaps where 3 to 5 keys are depressed at once during rapid chording. While 6KRO is sufficient for most typists, NKRO guarantees zero dropped inputs regardless of speed.

### Q2: Why does my rhythm game drop inputs on a 6KRO keyboard?
In rhythm games like *Osu! Lazer* or *Beatmania*, complex chords require pressing 7 or 8 keys at the exact same millisecond. A 6KRO keyboard will drop the 7th key, causing a missed note judgment.

---

## 🔗 Related Documentation & Links

- [Documentation Portal Home](index.md)
- [Ghosting & Matrix Diagnostics](ghosting-test.md)
- [Anti-Ghosting Hardware Guide](anti-ghosting.md)
- [Keyboard Latency & Polling Rates](keyboard-latency.md)
- [Master 100-Question FAQ Repository](faq.md)
