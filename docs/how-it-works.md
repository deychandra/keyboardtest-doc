<!--
SEO Title: How Online Keyboard Testing Works | W3C KeyboardEvent API
Meta Description: Technical deep dive into how KeyboardTest.tech captures keystrokes in HTML5. Learn about KeyboardEvent.code vs key, DOM event bubbling, and browser sandboxing.
Primary Keyword: how keyboard testing works
Secondary Keywords: KeyboardEvent code vs key, W3C keyboard event spec, browser keyboard event listener, web keyboard test architecture
URL Slug: docs/how-it-works.md
Suggested Internal Links: docs/getting-started.md, docs/keyboard-test.md, docs/keyboard-latency.md, docs/browser-support.md, docs/faq.md
External Reference Suggestions: W3C UI Events Specification for Keyboard Events (w3.org)
-->

# How Keyboard Testing Works Under the Hood

Welcome to the technical architectural deep dive of **KeyboardTest.tech**. This manual explains the internal DOM event processing model, W3C KeyboardEvent specs, physical vs. virtual key mapping, event listeners, and browser security sandboxing.

---

## 📋 Overview

**KeyboardTest.tech** operates entirely as a modern client-side Web application built using Vanilla TypeScript and standard HTML5 Web APIs. It contains no server-side keystroke processing, zero external binary dependencies, and zero ActiveX or Java applet plugins.

Understanding how web browsers capture and handle keyboard input provides insight into why KeyboardTest.tech achieves sub-millisecond event tracking accuracy across all operating systems.

---

## 🎯 Purpose & Architectural Goals

```
 ┌─────────────────────────────────────────────────────────────────────────────┐
 │                    KeyboardTest.tech Client-Side Architecture               │
 ├─────────────────────────┬─────────────────────────┬─────────────────────────┤
 │ 1. DOM Event Binding    │ 2. Scancode Abstraction │ 3. GPU-Accelerated UI   │
 │ Global window keydown/  │ Uses W3C KeyboardEvent  │ Direct Canvas / DOM     │
 │ keyup event listeners   │ .code for layout safety │ matrix element updates  │
 └─────────────────────────┴─────────────────────────┴─────────────────────────┘
```

1. **Physical Layout Decoupling:** Use physical position codes (`event.code`) rather than locale-dependent characters (`event.key`) to ensure accurate key mapping on QWERTY, QWERTZ, AZERTY, and Dvorak keyboards.
2. **Zero Input Delay:** Eliminate DOM reflow bottlenecks through hardware-accelerated rendering pipelines (`requestAnimationFrame`).
3. **100% Security Sandbox Compliance:** Operate strictly within browser security boundaries without requesting elevated system administrator privileges.

---

## 🔬 The W3C `KeyboardEvent` Interface

When a physical key is pressed, the web browser generates a W3C-compliant `KeyboardEvent` object containing critical diagnostic properties:

```typescript
interface KeyboardEvent extends UIEvent {
  readonly code: string;       // e.g., "KeyA", "Space", "NumpadEnter"
  readonly key: string;        // e.g., "a", "A", "Enter"
  readonly location: number;   // 0=Standard, 1=Left, 2=Right, 3=Numpad
  readonly repeat: boolean;    // true if auto-repeated by OS
  readonly altKey: boolean;    // true if Alt held
  readonly ctrlKey: boolean;   // true if Ctrl held
  readonly shiftKey: boolean;  // true if Shift held
  readonly metaKey: boolean;   // true if Command/Windows held
}
```

### 1. `event.code` vs. `event.key` (Crucial Technical Difference)

- **`event.code` (Physical Key Location):**  
  Represents the physical switch position on the keyboard layout regardless of operating system language settings.
  - Pressing the key immediately to the right of `Tab` on a US QWERTY board returns `code: "KeyQ"`.
  - Pressing the exact same physical key on a French AZERTY board STILL returns `code: "KeyQ"`, even though the character generated is `"a"`.
  - **Why KeyboardTest.tech uses `event.code`:** It guarantees that the visual virtual matrix lights up the exact physical key cap you pressed on your desk!

- **`event.key` (Logical String Value):**  
  Represents the character or function string produced by the key in the current OS input locale (e.g., `"q"`, `"Q"`, `"à"`, `"Enter"`).

---

## 🛠️ The Core Event Handling Lifecycle

```
[ Physical Key Press ]
         │
         ▼
[ OS Keyboard Driver ]
         │
         ▼
[ Web Browser Window Object ] ─── (Capture Phase) ───► window.addEventListener('keydown')
         │                                                      │
         │                                                      ▼
         │                                            [ Extract event.code ]
         │                                                      │
         │                                                      ▼
         │                                            [ Update Canvas UI State ]
         │                                                      │
         ▼                                                      ▼
[ Default Browser Action ] ◄─── (preventDefault) ────── [ Suppress Page Scroll ]
```

### JavaScript Implementation Pattern:

```typescript
// Attach listeners to global window object
window.addEventListener('keydown', (event: KeyboardEvent) => {
  // Prevent browser default actions (e.g. Backspace navigating back, Space scrolling down)
  if (shouldPreventDefault(event.code)) {
    event.preventDefault();
  }

  const keyElement = document.querySelector(`[data-code="${event.code}"]`);
  if (keyElement) {
    if (event.repeat) {
      keyElement.classList.add('repeating');
    } else {
      keyElement.classList.remove('tested');
      keyElement.classList.add('active');
    }
  }
}, { capture: true, passive: false });

window.addEventListener('keyup', (event: KeyboardEvent) => {
  const keyElement = document.querySelector(`[data-code="${event.code}"]`);
  if (keyElement) {
    keyElement.classList.remove('active', 'repeating');
    keyElement.classList.add('tested');
  }
}, { capture: true });
```

---

## 💡 Browser Security & Sandboxing Restrictions

Because web applications run inside a secure browser sandbox, browser developers enforce intentional security restrictions that impact keyboard testing:

1. **System-Level Hotkey Interception:**  
   Operating systems intercept global OS shortcuts (such as `Ctrl + Alt + Del` on Windows or `Cmd + Option + Esc` on Mac) before passing them to the browser window.
2. **Tab Focus Requirement:**  
   To prevent malicious background sites from recording keystrokes typed into other applications (keylogging prevention), browsers suspend `KeyboardEvent` delivery when a browser tab loses focus.

---

## ❓ Frequently Asked Questions

### Q1: Why does pressing `F5` refresh the page during testing?
By default, `F5` is mapped by web browsers to reload the active document. KeyboardTest.tech calls `event.preventDefault()` when focused to suppress default reloads, allowing `F5` to be tested safely.

### Q2: Does KeyboardTest.tech use WebHID API?
For standard testing, standard W3C `KeyboardEvent` APIs are used for universal compatibility. For advanced mechanical keyboard raw scancode mapping, WebHID API is optionally supported in Chromium browsers.

---

## 🔗 Related Documentation & Links

- [Documentation Portal Home](index.md)
- [Browser Compatibility Matrix](browser-support.md)
- [Keyboard Latency Diagnostics](keyboard-latency.md)
- [Master 100-Question FAQ Repository](faq.md)
