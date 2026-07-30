<!--
SEO Title: 100 Frequently Asked Questions (FAQ) | KeyboardTest.tech
Meta Description: The master 100-question FAQ repository for keyboard testing, ghosting, anti-ghosting, NKRO, mechanical switches, latency, and OS troubleshooting.
Primary Keyword: keyboard test FAQ
Secondary Keywords: keyboard testing questions, ghosting test FAQ, nkro FAQ, mechanical keyboard FAQ, keyboard repair questions
URL Slug: docs/faq.md
Suggested Internal Links: docs/getting-started.md, docs/keyboard-test.md, docs/ghosting-test.md, docs/anti-ghosting.md, docs/nkro.md, docs/keyboard-latency.md, docs/troubleshooting.md
External Reference Suggestions: W3C UI Events Specification & USB Implementers Forum
-->

# 100 Frequently Asked Questions (FAQ) Master Repository

Welcome to the definitive **100-Question FAQ Repository** for **KeyboardTest.tech**. This master reference index provides clear, concise, authoritative answers across 10 critical technical domains.

---

## 📚 Table of Contents by Domain

1. [General Keyboard Testing (Q1–Q10)](#1-general-keyboard-testing-q1q10)
2. [Keyboard Ghosting & Matrix Testing (Q11–Q20)](#2-keyboard-ghosting--matrix-testing-q11q20)
3. [Anti-Ghosting Hardware & Engineering (Q21–Q30)](#3-anti-ghosting-hardware--engineering-q21q30)
4. [N-Key Rollover (NKRO) & 6KRO (Q31–Q40)](#4-n-key-rollover-nkro--6kro-q31q40)
5. [Input Latency & USB Polling Rates (Q41–Q50)](#5-input-latency--usb-polling-rates-q41q50)
6. [Mechanical Keyboards & Switches (Q51–Q60)](#6-mechanical-keyboards--switches-q51q60)
7. [Gaming Keyboards & Rapid Trigger (Q61–Q70)](#7-gaming-keyboards--rapid-trigger-q61q70)
8. [Laptop Keyboards & Portable Devices (Q71–Q80)](#8-laptop-keyboards--portable-devices-q71q80)
9. [Hardware Troubleshooting & Repair (Q81–Q90)](#9-hardware-troubleshooting--repair-q81q90)
10. [Browser & Operating System Compatibility (Q91–Q100)](#10-browser--operating-system-compatibility-q91q100)

---

## 1. General Keyboard Testing (Q1–Q10)

#### Q1: What is KeyboardTest.tech?
KeyboardTest.tech is a free, professional, browser-based keyboard testing utility that allows users to verify keypress detection, test for stuck keys, analyze matrix ghosting, and check N-Key Rollover without installing software.

#### Q2: Is KeyboardTest.tech 100% free to use?
Yes. The complete diagnostic suite is free for personal, commercial, educational, and professional diagnostic use.

#### Q3: Do I need to download or install software to test my keyboard?
No. KeyboardTest.tech operates 100% inside your web browser using HTML5 and Vanilla TypeScript APIs.

#### Q4: Does KeyboardTest.tech store or record my keystrokes?
No. All event listener processing occurs locally within your browser's RAM. Zero keystrokes are recorded, stored, or transmitted.

#### Q5: What do the visual key colors mean on the test board?
Gray means Untested, Cyan/Blue means Currently Pressed (Active), Green means Successfully Tested, and Red means Stuck or Error state.

#### Q6: How do I reset the visual keyboard canvas?
Click the bright **"Reset Board"** button above the virtual matrix to clear highlighted states.

#### Q7: Can I test external USB and Bluetooth keyboards?
Yes. KeyboardTest.tech tests any physical input device that connects via USB, 2.4GHz RF wireless, or Bluetooth.

#### Q8: What physical layout options are supported?
KeyboardTest.tech supports 104-key ANSI (US), 105-key ISO (UK/European), Apple Mac, TKL (80%), 75%, 65%, and 60% layouts.

#### Q9: What is the Live Key Data Inspector?
It is a real-time diagnostic panel that displays raw `event.code`, `event.key`, `event.location`, and press duration timestamps.

#### Q10: How long does a complete keyboard test take?
A full 104-key diagnostic audit takes less than 30 seconds by pressing keys sequentially.

---

## 2. Keyboard Ghosting & Matrix Testing (Q11–Q20)

#### Q11: What is keyboard ghosting?
Ghosting occurs when pressing multiple keys simultaneously causes an unpressed third key to register (a phantom keypress) due to shared PCB traces.

#### Q12: Why does keyboard ghosting happen on membrane boards?
Membrane keyboards organize keys in a grid matrix of rows and columns to save costs, allowing current to bleed across adjacent circuits.

#### Q13: How do I perform a ghosting test on KeyboardTest.tech?
Hold down common multi-key gaming combinations (e.g., `W + A + Shift + Space`) and verify if all pressed keys illuminate without phantom inputs.

#### Q14: What is a phantom keypress?
A phantom keypress is an unpressed key that lights up on screen because electric current flowed backward through an uninsulated matrix intersection.

#### Q15: What is key blocking?
Key blocking is a firmware safeguard where the keyboard controller suppresses 3rd or 4th simultaneous keypresses to prevent sending phantom keys.

#### Q16: Can ghosting ruin gaming performance?
Yes. In FPS or rhythm games, ghosting causes missed jump, sprint, or directional inputs when holding multiple movement keys.

#### Q17: Does keyboard ghosting affect typing speed?
Fast touch-typists exceeding 120 WPM may experience dropped or rearranged characters if their keyboard suffers from matrix ghosting.

#### Q18: Are laptop keyboards susceptible to ghosting?
Yes. Most laptop keyboards use compact membrane trace ribbons optimized for typing rather than multi-key gaming combos.

#### Q19: Can software fix hardware matrix ghosting?
No. Matrix ghosting is a physical PCB circuit limitation. You can only bypass it by rebinding keys to separate matrix rows or upgrading hardware.

#### Q20: How does KeyboardTest.tech highlight ghosting?
Unpressed keys that trigger due to ghosting light up automatically, while blocked keys fail to light up when physically depressed.

---

## 3. Anti-Ghosting Hardware & Engineering (Q21–Q30)

#### Q21: What is an anti-ghosting keyboard?
An anti-ghosting keyboard incorporates circuit isolation (diodes or optimized trace routing) to ensure every pressed key registers accurately.

#### Q22: How do anti-ghosting diodes work?
Signal diodes (such as 1N4148 or SMD diodes) permit electric current to flow in only one direction, physically blocking reverse current bleed.

#### Q23: What is 26-Key Anti-Ghosting?
It is a membrane keyboard design where trace lines for the 26 most popular gaming keys (WASD, Arrows, Space, Shift, Ctrl) are rerouted to prevent ghosting.

#### Q24: What is Full-Board Anti-Ghosting?
Full-Board Anti-Ghosting assigns a dedicated switching diode to every single key switch on the PCB, providing 100% ghosting protection.

#### Q25: Do mechanical keyboards have built-in anti-ghosting?
Almost all modern mechanical keyboards feature diode-isolated PCBs, providing full-board anti-ghosting out of the box.

#### Q26: Do optical keyboards have anti-ghosting?
Yes. Optical keyboards use light beams instead of metal contact leaves, completely avoiding electrical matrix ghosting.

#### Q27: How can I verify if my keyboard has true anti-ghosting?
Press down 10 keys simultaneously across the board on KeyboardTest.tech. If all 10 register green without errors, anti-ghosting is functional.

#### Q28: Is anti-ghosting the same as N-Key Rollover (NKRO)?
Anti-ghosting prevents *false phantom keys*, while NKRO allows an *unlimited number of legitimate keys* to register simultaneously.

#### Q29: Does anti-ghosting require special drivers?
No. Anti-ghosting is a physical hardware circuit property that operates automatically without drivers.

#### Q30: Do custom hot-swap PCBs support anti-ghosting?
Yes. Custom mechanical keyboard PCBs (QMK/VIA compatible) feature SMD diodes pre-soldered next to every hot-swap socket.

---

## 4. N-Key Rollover (NKRO) & 6KRO (Q31–Q40)

#### Q31: What does NKRO stand for?
NKRO stands for **N-Key Rollover**, where `N` represents an unlimited number of simultaneous keypresses.

#### Q32: What is 6KRO?
6KRO (6-Key Rollover) is a standard USB HID protocol limit allowing a maximum of 6 standard alphanumeric keys plus modifier keys to register at once.

#### Q33: Why does the standard USB protocol limit keyboards to 6KRO?
Legacy USB HID boot protocol specification restricts keyboard report buffers to 8 bytes (1 byte for modifiers, 1 reserved byte, 6 bytes for key codes).

#### Q34: How do gaming keyboards achieve NKRO over USB?
They use composite HID report descriptors or bitmap arrays (128-bit key bitfields) to emulate multiple virtual keyboards over a single USB connection.

#### Q35: How do I test NKRO on KeyboardTest.tech?
Press down as many keys as possible simultaneously using both hands and check the **Simultaneous Key Counter**.

#### Q36: Is NKRO supported over Bluetooth?
Most Bluetooth profiles restrict connections to 6KRO to conserve battery life, though some modern Bluetooth 5.0 gaming boards support NKRO.

#### Q37: What is the advantage of NKRO in rhythm games?
Rhythm games (*Osu!*, *Beatmania*, *DDR*) require pressing 7 to 10 keys on the exact same millisecond, which fails on 6KRO boards.

#### Q38: Why does my NKRO keyboard fail in motherboard BIOS screens?
Older motherboard BIOS software only understands basic 6KRO USB boot protocol packets. Use your keyboard's `Fn` hotkey to toggle 6KRO mode for BIOS setup.

#### Q39: Does PS/2 support native NKRO?
Yes. Legacy PS/2 motherboard ports use hardware interrupts rather than polled buffers, supporting native unbuffered NKRO.

#### Q40: What is 10KRO?
10KRO allows up to 10 simultaneous keypresses (one for each finger), which is sufficient for touch-typing and most gaming scenarios.

---

## 5. Input Latency & USB Polling Rates (Q41–Q50)

#### Q41: What is keyboard input latency?
Keyboard latency is the total time delay between physically pressing a key switch stem and the event registering in the operating system or game engine.

#### Q42: What is USB polling rate?
USB polling rate is the frequency (measured in Hertz) at which the host CPU requests input data updates from the keyboard controller.

#### Q43: What latency does a 1000Hz polling rate provide?
A 1000Hz polling rate queries the keyboard every 1.0 millisecond ($1/1000\text{ sec} = 1\text{ ms}$).

#### Q44: What latency does an 8000Hz polling rate provide?
An 8000Hz polling rate queries the keyboard every 0.125 milliseconds ($1/8000\text{ sec} = 0.125\text{ ms}$).

#### Q45: What is switch debouncing delay?
Debouncing delay is a necessary software delay ($2\text{ms}$ to $10\text{ms}$) added by microcontrollers to ignore rapid mechanical contact leaf vibration (chatter).

#### Q46: Do optical switches have debouncing delay?
No. Because optical switches use light beams rather than colliding metal contacts, they feature $0\text{ ms}$ debouncing delay.

#### Q47: How does KeyboardTest.tech measure key latency?
KeyboardTest.tech uses the W3C High Resolution Time API (`performance.now()`) with microsecond sub-millisecond precision.

#### Q48: Does wireless gaming add input latency?
Modern 2.4GHz RF wireless (Logitech LIGHTSPEED, Razer HyperSpeed) matches wired 1000Hz performance with sub-1ms latency. Bluetooth, however, adds 10-20ms lag.

#### Q49: Does monitor refresh rate affect visual testing latency?
Yes. High refresh rate monitors (144Hz, 240Hz, 360Hz) render visual key highlights faster, reducing visual display lag.

#### Q50: How can I lower my keyboard latency for competitive gaming?
Plug directly into motherboard USB ports, set polling rate to 1000Hz+, use optical/magnetic switches, and enable GPU hardware acceleration in your browser.

---

## 6. Mechanical Keyboards & Switches (Q51–Q60)

#### Q51: What is a mechanical keyboard?
A mechanical keyboard uses individual physical electromechanical switch assemblies under every keycap rather than a shared rubber membrane sheet.

#### Q52: What are Linear mechanical switches?
Linear switches (e.g., Cherry MX Red) provide smooth, silent, uninterrupted downward travel from top to bottom.

#### Q53: What are Tactile mechanical switches?
Tactile switches (e.g., Cherry MX Brown, Boba U4T) provide a physical tactile bump at the actuation point to confirm key registration.

#### Q54: What are Clicky mechanical switches?
Clicky switches (e.g., Cherry MX Blue) produce both a tactile bump and an audible click sound at the point of actuation.

#### Q55: What is a Hot-Swap PCB?
A Hot-Swap PCB features pre-soldered metal sockets, allowing users to swap mechanical switches without soldering.

#### Q56: What is key chatter (double typing)?
Key chatter occurs when oxidized or damaged metal contacts bounce rapidly, causing a single physical press to type two letters (e.g., `"ttest"`).

#### Q57: How do I test a hot-swap PCB before building?
Bridge the two metal contacts of each socket on the bare PCB using conductive metal tweezers while watching KeyboardTest.tech.

#### Q58: What is QMK / VIA firmware?
QMK and VIA are open-source keyboard firmware frameworks that allow users to remap key layers, macros, and actuation behaviors.

#### Q59: What is actuation distance?
Actuation distance is the physical depth (typically 1.2mm to 2.0mm) a key stem must travel before triggering an electrical signal.

#### Q60: What is total travel distance?
Total travel distance is the full physical distance (typically 3.5mm to 4.0mm) from rest position to bottoming out against the PCB plate.

---

## 7. Gaming Keyboards & Rapid Trigger (Q61–Q70)

#### Q61: What is a Hall Effect (HE) magnetic switch?
A Hall Effect switch uses a permanent magnet and a Hall sensor to measure key position continuously based on magnetic field strength.

#### Q62: What is Rapid Trigger technology?
Rapid Trigger dynamically resets and reactuates a magnetic key switch the instant it moves upward or downward by $0.1\text{ mm}$, regardless of physical travel position.

#### Q63: Why is Rapid Trigger crucial for FPS games like CS2 and Valorant?
Rapid Trigger enables instant counter-strafing, stopping player movement momentum immediately to gain first-shot accuracy.

#### Q64: What is SOCD (Single Origin Command Device) / Snappy Taps?
SOCD firmware resolution prioritizes the most recently pressed directional key (e.g., pressing `D` automatically overrides `A` without holding both).

#### Q65: Can I test Rapid Trigger sensitivity on KeyboardTest.tech?
Yes. Set actuation to minimum ($0.1\text{mm}$) in your software and tap lightly to verify instant press and release responses on screen.

#### Q66: What is an Optical gaming switch?
An optical switch uses an infrared light beam that is interrupted or restored when the key stem moves downward.

#### Q67: What is a 60% layout gaming keyboard?
A 60% layout omits the Arrow cluster, Function row, and Numpad, providing maximum desk space for low-DPI mouse movement.

#### Q68: Are low-profile mechanical switches good for gaming?
Yes. Low-profile switches feature shorter total travel (2.5mm - 3.0mm), offering faster physical actuation.

#### Q69: Why do gaming keyboards use braided USB-C cables?
Braided USB-C cables offer enhanced durability, electromagnetic interference shielding, and easy detachment for LAN tournaments.

#### Q70: Does RGB lighting affect keyboard polling performance?
On well-engineered keyboards with dedicated LED microcontrollers, RGB lighting does not impact input latency or polling rates.

---

## 8. Laptop Keyboards & Portable Devices (Q71–Q80)

#### Q71: What switch mechanism do laptop keyboards use?
Most laptop keyboards use scissor-switch membrane mechanisms, combining rubber domes with plastic X-frame stabilizers.

#### Q72: How do I test my laptop keyboard for dead keys on KeyboardTest.tech?
Open [KeyboardTest.tech](https://keyboardtest.tech), select your OS layout (Mac/Windows/Chromebook), and press every key sequentially.

#### Q73: Why do some laptop keys stop working after a liquid spill?
Sticky liquids corrode delicate printed silver matrix traces on thin plastic membrane sheets, creating open circuit breaks.

#### Q74: Can laptop keys be replaced individually?
Scissor keycaps and rubber domes can be snapped off and replaced, but underlying broken matrix traces require replacing the entire upper palmrest assembly.

#### Q75: How do I test special top-row keys on Chromebooks?
KeyboardTest.tech supports ChromeOS layout mappings, capturing top-row action keys (Back, Refresh, Fullscreen, App Switcher, Brightness).

#### Q76: Why does pressing `Fn` on my laptop not register on screen?
The `Fn` key is a hardware-level multiplexer on laptops that changes scancodes internally before sending events to the OS.

#### Q77: Does KeyboardTest.tech work on Apple MacBook Magic Keyboards?
Yes. Select the **Mac Layout** option to view Apple-specific Command (`⌘`), Option (`⌥`), and Control (`⌃`) key states.

#### Q78: Can I test a Microsoft Surface Type Cover keyboard?
Yes. Detachable Surface keyboards send standard Windows `KeyboardEvent` signals over internal pogo pins.

#### Q79: Why does my laptop keyboard double-type certain letters?
Debris or moisture trapped under the rubber dome causes intermittent contact bounce. Clean under the keycap with compressed air.

#### Q80: How do I disable a built-in laptop keyboard when using an external board?
In Windows Device Manager, disable the "Standard PS/2 Keyboard" driver, or use third-party utility software.

---

## 9. Hardware Troubleshooting & Repair (Q81–Q90)

#### Q81: What should I do if a single key stops working completely?
Clean around the switch stem with compressed air, apply 99% isopropyl alcohol, or replace the switch if using a hot-swap PCB.

#### Q82: What does an entire dead row of keys indicate?
An entire dead row or column indicates a cracked PCB trace line, a blown diode, or a damaged microcontroller pin.

#### Q83: What is the immediate first step during a liquid spill?
Unplug the USB cable or switch off battery power within 3 seconds to prevent electrical short-circuiting.

#### Q84: How long should a keyboard dry after a liquid spill?
Allow at least 24 to 48 hours of inverted air drying in a warm, ventilated area before reapplying electrical power.

#### Q85: How do I remove sticky soda residue from mechanical switches?
Clean the switch plate and housing using 99% Isopropyl Alcohol (IPA) and cotton swabs. Avoid using water or conductive cleaners.

#### Q86: Why does my key stay red (stuck state) on KeyboardTest.tech?
A red key highlight indicates the browser received a `keydown` event but no `keyup` release event, pointing to a physically stuck switch stem or debris.

#### Q87: How do I test for cold solder joints on a soldered PCB?
Inspect the underside of the PCB for dull, cracked solder balls around switch pins. Re-flow cracked joints with a soldering iron.

#### Q88: Why do my arrow keys type numbers instead of moving the cursor?
Your Numpad `Num Lock` key is toggled off, or your keyboard is operating in Numpad emulation mode. Press `Num Lock` to restore arrow navigation.

#### Q89: Can a damaged USB cable cause intermittent disconnects?
Yes. Internal copper wire fraying near the USB strain relief boot causes the keyboard to drop connection during physical desk movement.

#### Q90: How do I test if my issue is hardware or software related?
Test the keyboard on KeyboardTest.tech on a second computer or smartphone via USB-OTG. If the issue persists on another device, it is a hardware fault.

---

## 10. Browser & Operating System Compatibility (Q91–Q100)

#### Q91: Does KeyboardTest.tech support Google Chrome?
Yes. Chrome (Blink engine) provides 100% full compatibility, including `KeyboardEvent.code` and optional WebHID API support.

#### Q92: Does KeyboardTest.tech support Mozilla Firefox?
Yes. Firefox (Gecko engine) provides full compatibility for key press detection, high-resolution timing, and matrix layouts.

#### Q93: Does KeyboardTest.tech support Apple Safari on macOS and iOS?
Yes. Safari is fully supported. Mac modifier keys (`⌘`, `⌥`, `⌃`) are automatically normalized.

#### Q94: Does KeyboardTest.tech work on Microsoft Edge?
Yes. Microsoft Edge runs on the Chromium Blink engine, offering identical performance and feature support as Chrome.

#### Q95: Why does `F11` toggle full screen instead of highlighting on screen?
`F11` is a browser-reserved shortcut for full-screen toggle. KeyboardTest.tech calls `event.preventDefault()` when focused to capture `F11`.

#### Q96: Why do keystrokes fail to register when clicking another window?
Web browsers suspend `KeyboardEvent` delivery to unfocused background tabs to protect user privacy against background keylogging.

#### Q97: How does Linux handle keyboard scancodes on Wayland vs X11?
KeyboardTest.tech relies on browser-standard W3C event abstractions, ensuring consistent `event.code` mapping on both Wayland and X11 display servers.

#### Q98: Can browser extensions block keyboard test events?
Yes. Extensions like Vimium, Tridactyl, or password managers may intercept `Tab`, `Esc`, or navigation keys. Test in Incognito mode.

#### Q99: Does KeyboardTest.tech work on Linux ARM devices (Raspberry Pi)?
Yes. Any ARM Linux device running standard Chromium or Firefox supports full diagnostic testing on KeyboardTest.tech.

#### Q100: Is my privacy guaranteed when using KeyboardTest.tech?
Yes. All testing logic executes 100% locally in your browser's RAM sandbox. Zero key data is logged, recorded, or transmitted to any server.

---

## 🔗 Related Documentation & Links

- [Documentation Portal Home](index.md)
- [Getting Started Guide](getting-started.md)
- [Keyboard Press Test Guide](keyboard-test.md)
- [Ghosting Diagnostic Guide](ghosting-test.md)
- [N-Key Rollover (NKRO) Manual](nkro.md)
- [Keyboard Latency & Timing Manual](keyboard-latency.md)
- [Hardware Troubleshooting Tree](troubleshooting.md)
