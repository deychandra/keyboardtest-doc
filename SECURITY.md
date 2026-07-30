# Security Policy

At **KeyboardTest.tech**, security and privacy are fundamental pillars of our web architecture. Because our online keyboard testing software operates 100% locally inside the client browser without sending keystrokes or hardware events to remote servers, user security is guaranteed by design.

---

## Supported Versions

We maintain security updates and patches for the live production release of KeyboardTest.tech.

| Version | Supported |
| ------- | --------- |
| 2.x.x   | :white_check_mark: Yes |
| 1.x.x   | :x: No (Deprecated) |

---

## Architecture & Data Privacy Guarantee

1. **Zero Keystroke Storage:** KeyboardTest.tech does **not** record, log, store, transmit, or analyze any keystrokes pressed during your diagnostic session.
2. **Client-Side Event Model:** All keystroke testing uses standard HTML5 `KeyboardEvent` JavaScript events executed locally within your browser sandbox.
3. **No External Tracking of Keystrokes:** Keystroke telemetry is never transmitted to analytics providers, third-party databases, or cloud servers.

---

## Reporting a Vulnerability

If you discover a potential security vulnerability within the KeyboardTest.tech platform or documentation repository, please notify us responsibly rather than opening a public issue.

### Submission Guidelines
- **Email:** Send details to `security@keyboardtest.tech`.
- **Details to Include:**
  - Description of the vulnerability or concern.
  - Steps to reproduce the issue.
  - Affected browser engine or operating system (if applicable).
  - Proof-of-concept (PoC) code or script if relevant.

### Response Timelines
- **Initial Acknowledgment:** Within 48 hours.
- **Triage & Status Assessment:** Within 5 business days.
- **Public Disclosure:** Coordinated after a patch or fix has been verified and deployed.

Thank you for maintaining the security and privacy of KeyboardTest.tech users worldwide.
