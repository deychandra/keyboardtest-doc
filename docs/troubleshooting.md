<!--
SEO Title: Keyboard Troubleshooting & Hardware Repair Tree | KeyboardTest.tech
Meta Description: Comprehensive diagnostic decision tree for broken keys, stuck switches, key chatter, liquid spill recovery, and OS driver remappings.
Primary Keyword: keyboard troubleshooting
Secondary Keywords: fix broken keyboard key, stuck key fix, keyboard liquid spill repair, key chatter fix, keyboard not working diagnostic
URL Slug: docs/troubleshooting.md
Suggested Internal Links: docs/getting-started.md, docs/keyboard-test.md, docs/ghosting-test.md, docs/mechanical-keyboards.md, docs/faq.md
External Reference Suggestions: Microsoft Windows Device Manager Troubleshooting Guides
-->

# Comprehensive Keyboard Troubleshooting & Hardware Diagnostic Manual

Welcome to the **Hardware Troubleshooting & Repair Tree** on **KeyboardTest.tech**. When a key fails to respond, stuck keys output endless characters, or liquid spills threaten your hardware, systematic isolation is essential. This manual provides a step-by-step diagnostic tree to isolate physical hardware defects from software conflicts.

---

## 📋 Overview

Keyboard failure can stem from five distinct layers:
1. **Physical Mechanism:** Debris, broken switch stems, liquid residue, or bent contact leaves.
2. **PCB Electronics:** Lifted hot-swap sockets, blown anti-ghosting diodes, or cracked trace lines.
3. **Hardware Connectivity:** Damaged USB cables, faulty Bluetooth receivers, or unpowered USB hubs.
4. **OS Drivers & Remappings:** Corrupted device driver stacks or active remapping scripts (AutoHotkey/Karabiner).
5. **Browser DOM Layer:** Out-of-focus tabs or intercepting browser extensions.

---

## 🌳 Diagnostic Decision Tree

```
                          [ Key Malfunction Observed ]
                                       │
                    Is the problem isolated to ONE key or MULTIPLE keys?
                   ┌───────────────────┴───────────────────┐
             [ ONE KEY ]                             [ MULTIPLE KEYS / ROW ]
                   │                                       │
      Does it fire ONCE or TWICE?            Is an entire ROW or COLUMN dead?
     ┌─────────────┴─────────────┐                 ┌───────┴───────┐
 [ NO RESPONSE ]           [ CHATTER / DOUBLE ]  [ YES ]        [ NO ]
     │                           │                 │               │
  Clean Switch &              Replace Switch /   Blown Diode /   Driver / OS
  Check PCB Socket            Increase Debounce  PCB Trace Crack Conflict
```

---

## 🛠️ Step-by-Step Diagnostic & Repair Procedures

### Scenario 1: A Single Key Does Not Respond At All

#### Step 1: Rule Out Browser Interception
- Open **[KeyboardTest.tech](https://keyboardtest.tech)** in an **Incognito / Private Window**.
- If testing `F1`-`F12`, `Esc`, or `Tab`, ensure third-party browser extensions (Vimium, Bitwarden) are disabled.

#### Step 2: Inspect Scancode Output in Data Inspector
- Press the non-responsive key. Look at the **Live Key Data Inspector**:
  - **Case A: No event appears.** The physical signal is not reaching the OS (hardware switch or PCB fault).
  - **Case B: Event code appears, but wrong letter outputs.** Software remapping is active in the OS.

#### Step 3: Physical Mechanical Cleaning
- Disconnect the keyboard.
- Remove the keycap using a wire keycap puller.
- Use compressed air to blow out dust from around the switch stem.
- For mechanical switches, apply 2 drops of 99% isopropyl alcohol directly inside the switch stem, actuate 30 times, and allow 15 minutes to dry.

---

### Scenario 2: Key Chatter (Single Press Types Double Letters: "t-t-est")

#### Step 1: Test Chatter on KeyboardTest.tech
- Press the key lightly 10 times. Inspect the event log.
- If multiple `keydown` events fire within $<15\text{ ms}$, contact leaf bounce is failing.

#### Step 2: Software Mitigation vs. Hardware Repair
- **Software Fix:** In Windows Filter Keys or custom keyboard software (QMK/VIA), increase the **Debounce Delay** from $5\text{ ms}$ to $10\text{ ms}$.
- **Hardware Fix (Hot-Swap):** Replace the mechanical switch with a new switch.

---

### Scenario 3: Liquid Spill Emergency Protocol

If coffee, water, or soda is spilled on your keyboard, follow this immediate emergency protocol to prevent permanent PCB corrosion:

```
[ 1. UNPLUG IMMEDIATELY ] ───► [ 2. DO NOT PRESS KEYS ] ───► [ 3. INVERT & DRAIN ]
   Disconnect USB / Power        Prevents short circuits       Drain liquid downward
                                                                       │
                                                                       ▼
[ 5. AUDIT ON KEYBOARDTEST ] ◄── [ 4. 99% ISOPROPYL CLEAN ] ◄── [ 24-48 HR DRY ]
   Verify 100% matrix status      Clean sticky residue          Complete air drying
```

1. **Unplug Immediately:** Disconnect the USB cable or switch off battery power within 3 seconds. Do NOT attempt to shut down Windows gracefully first!
2. **Invert the Keyboard:** Flip the keyboard upside down over a towel so liquid drains away from the internal PCB.
3. **Disassemble & Clean:** Remove keycaps and case backplate. Wash sticky soda residue with 99% Isopropyl Alcohol (IPA).
4. **Air Dry for 24-48 Hours:** Allow complete evaporation before reapplying power.
5. **Verify Matrix on KeyboardTest.tech:** Reconnect and test every key to confirm no shorted rows exist.

---

## ❓ Frequently Asked Questions

### Q1: Why is an entire column of keys dead on my keyboard?
An entire dead column (e.g., `1, Q, A, Z` all failing together) indicates a severed PCB column trace line or a damaged microcontroller pin rather than individual switch failure.

### Q2: How do I remove stuck OS key remappings?
In Windows, check Task Manager for AutoHotkey scripts, PowerToys Keyboard Manager, or SharpKeys registry mappings. On Mac, check System Settings -> Keyboard -> Keyboard Shortcuts.

---

## 🔗 Related Documentation & Links

- [Documentation Portal Home](index.md)
- [Getting Started Guide](getting-started.md)
- [Keyboard Press Test Guide](keyboard-test.md)
- [Mechanical Keyboard Guide](mechanical-keyboards.md)
- [Master 100-Question FAQ Repository](faq.md)
