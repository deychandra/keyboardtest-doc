# Supported Devices & Layouts Matrix

**KeyboardTest.tech** provides zero-installation hardware verification across a wide spectrum of keyboard form factors, operating systems, custom firmware, and switch technologies.

---

## 1. Supported Form Factors & Layouts

KeyboardTest.tech features real-time dynamic visual matrix rendering for the following physical layout form factors:

| Form Factor | Description | Key Count | Supported Layouts |
| ----------- | ----------- | --------- | ----------------- |
| **Full-Size (100%)** | Standard desktop keyboard with dedicated Numpad, Arrow Cluster, and Function Row. | 104 / 105 / 108 keys | ANSI, ISO, JIS |
| **Tenkeyless (TKL / 80%)** | Compact desktop layout omitting the dedicated number pad. | 87 / 88 keys | ANSI, ISO, Mac |
| **75% Layout** | Compact condensed layout retaining Function keys and Navigation cluster. | 82 - 84 keys | ANSI, ISO |
| **65% Layout** | Highly popular enthusiast layout with Arrow keys but no dedicated F-row. | 67 - 68 keys | ANSI, ISO |
| **60% Layout** | Minimalist compact layout utilizing Fn layer for arrow and function keys. | 61 - 62 keys | ANSI, ISO |
| **40% / Ortholinear** | Ultra-compact enthusiast keyboards (Planck, Preonic). | 40 - 48 keys | Custom Matrix |
| **Laptop Keyboards** | Integrated chiclet / membrane laptop keyboards (MacBook, ThinkPad, Dell XPS, Surface). | Variable | Mac / Windows / Chromebook |

---

## 2. Operating System & Platform Compatibility

| Platform | Supported Versions | Notes & System Specifics |
| -------- | ------------------ | ----------------------- |
| **Microsoft Windows** | Windows 11, 10, 8.1, 7 | Full native event code mapping (`VK_CODES`). Captures Windows key, NumLock, ScrollLock, PrintScreen. |
| **Apple macOS** | macOS Sequoia, Sonoma, Ventura, Monterey, Big Sur | Full Command (`⌘`), Option (`⌥`), Control (`⌃`), CapsLock LED, and Function (`Fn`) key support. |
| **Linux Distributions** | Ubuntu, Fedora, Arch, Debian, Linux Mint, Manjaro | X11 and Wayland display server event capture. Full support for Tux/Super key. |
| **Google ChromeOS** | Chromebooks, Chromeboxes (All Chrome OS versions) | Special top-row action key detection (Back, Refresh, Fullscreen, App Switcher, Brightness). |

---

## 3. Keyboard Hardware & Switch Technologies

KeyboardTest.tech accurately tests all underlying physical switch mechanisms:

- **Mechanical Keyboards:** Cherry MX, Gateron, Kailh, Outemu, Akko, JWK, Boba switches.
- **Magnetic / Hall Effect Keyboards:** Wooting, SteelSeries Apex Pro, Razer Huntsman V3, DrunkDeer, Endgame Gear (Rapid Trigger testing).
- **Optical Switch Keyboards:** Razer Opto-Mechanical, Corsair OPX, Bloody Light Strike.
- **Topre & Electrostatic Capacitive:** HHKB (Happy Hacking Keyboard), Realforce, Leopold Topre clones.
- **Membrane & Rubber Dome:** Office desktop keyboards, low-profile membrane keyboards.
- **Scissor-Switch Laptop Keyboards:** Apple Magic Keyboard, ThinkPad TrackPoint keyboards.
- **Custom Firmware Keyboards:** QMK, VIA, Vial, ZMK, OpenRGB compatible custom PCBs.

---

## 4. Hardware Connection Protocols

- **Standard Wired USB:** USB-A, USB-C (125Hz, 500Hz, 1000Hz, 4000Hz, 8000Hz USB polling rates).
- **Wireless Bluetooth:** Bluetooth 3.0 / 4.0 / 5.0 / 5.1 / 5.2 / 5.3 low energy connections.
- **2.4GHz RF Wireless:** Proprietary USB dongle wireless receivers (Logitech LIGHTSPEED, Razer HyperSpeed, Corsair SLIPSTREAM).
- **PS/2 Ports:** Legacy motherboards with PS/2 connections (supports full hardware NKRO).

---

## 5. Related Documentation & Guides
- [Browser Compatibility Matrix](SUPPORTED_BROWSERS.md)
- [Mechanical Keyboard Diagnostic Guide](docs/mechanical-keyboards.md)
- [Gaming Keyboard & Polling Rate Guide](docs/gaming-guide.md)
