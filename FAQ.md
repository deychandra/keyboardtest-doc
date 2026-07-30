# Master Frequently Asked Questions (FAQ) Directory

Welcome to the comprehensive **KeyboardTest.tech FAQ Directory**. Below is an index of our 100 answered questions covering keyboard hardware diagnostics, matrix ghosting, N-Key Rollover, input latency, gaming switches, and operating system troubleshooting.

---

## 📚 Quick Navigation by Category

1. [General Keyboard Testing & Diagnostics](#1-general-keyboard-testing--diagnostics)
2. [Keyboard Ghosting & Anti-Ghosting](#2-keyboard-ghosting--anti-ghosting)
3. [N-Key Rollover (NKRO) & 6KRO](#3-n-key-rollover-nkro--6kro)
4. [Keyboard Latency & Polling Rates](#4-keyboard-latency--polling-rates)
5. [Mechanical Keyboards & Switches](#5-mechanical-keyboards--switches)
6. [Gaming Keyboards & Esports Performance](#6-gaming-keyboards--esports-performance)
7. [Laptop Keyboards & Portable Devices](#7-laptop-keyboards--portable-devices)
8. [Troubleshooting & Hardware Repair](#8-troubleshooting--hardware-repair)
9. [Browser & OS Compatibility](#9-browser--os-compatibility)
10. [Security & Data Privacy](#10-security--data-privacy)

---

## 1. General Keyboard Testing & Diagnostics

### Q1.1: What is KeyboardTest.tech?
KeyboardTest.tech is a free, professional, browser-based keyboard testing utility that allows users to verify key press responsiveness, test for stuck or broken keys, analyze matrix ghosting, and check N-Key Rollover without installing software.

### Q1.2: Do I need to install software or drivers to use KeyboardTest.tech?
No. KeyboardTest.tech runs 100% inside any standard HTML5 web browser. No plugins, desktop applications, or elevated permissions are required.

### Q1.3: How do I test if all my keys are working?
Open [KeyboardTest.tech](https://keyboardtest.tech) and press every key on your keyboard one by one. As each key is pressed, its corresponding key on the visual virtual keyboard matrix will turn active and register as tested.

### Q1.4: What do the visual key highlight colors mean?
- **Gray/Dark:** Unpressed / Untested key.
- **Bright Blue / Cyan (Active):** Key is currently being held down.
- **Green (Tested):** Key was pressed successfully and released.
- **Red (Stuck / Error):** Key is stuck down or sending continuous signals without physical release.

---

## 2. Keyboard Ghosting & Anti-Ghosting

### Q2.1: What is keyboard ghosting?
Keyboard ghosting occurs when pressing multiple keys simultaneously causes an unpressed third key to register (a phantom keypress) or causes additional keys to fail to register at all due to shared electrical traces in cheap keyboard PCBs.

### Q2.2: How do I test my keyboard for ghosting?
Navigate to the [Ghosting Test](docs/ghosting-test.md) on KeyboardTest.tech, hold down common multi-key gaming combinations (e.g., `W + A + Shift + Space`), and verify if all pressed keys illuminate without dropping inputs.

---

## 3. N-Key Rollover (NKRO) & 6KRO

### Q3.1: What is N-Key Rollover (NKRO)?
N-Key Rollover means a keyboard can register as many keys as you can physically press down simultaneously (`N` = unlimited number of keys) without losing input signals or locking up.

### Q3.2: What is the difference between 6KRO and NKRO?
- **6KRO (6-Key Rollover):** Standard USB HID protocol limit allowing a maximum of 6 standard keys plus modifier keys (`Ctrl`, `Shift`, `Alt`) to be pressed simultaneously.
- **NKRO (N-Key Rollover):** Hardware and firmware capability allowing unlimited simultaneous keypresses.

---

## 4. Full FAQ Reference Repository

For the complete list of all **100 detailed questions and technical answers**, please visit our dedicated documentation pages:
- [Complete 100-Question FAQ Repository Guide](docs/faq.md)
- [Troubleshooting & Diagnostic Guide](docs/troubleshooting.md)
- [Gaming Keyboard & Switch Guide](docs/gaming-guide.md)
- [Mechanical Keyboard PCB Guide](docs/mechanical-keyboards.md)
