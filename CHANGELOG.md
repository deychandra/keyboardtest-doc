# Changelog

All notable changes to the **KeyboardTest.tech** platform documentation and browser utility will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

### Added
- Comprehensive GitHub Documentation Suite with over 20 structured technical guides.
- Detailed N-Key Rollover (NKRO) and ghosting diagnostic guides.
- Hardware latency and debouncing latency measurement manuals.
- 100-Question Frequently Asked Questions (FAQ) reference repository.
- GitHub Issue & Pull Request templates and automated CI validation workflows.

---

## [v2.4.0] - 2026-06-15

### Added
- WebHID diagnostic API support for advanced mechanical keyboard layout detection.
- Interactive ISO and ANSI layout toggle on the main keyboard test suite.
- High-rate polling detection support up to 8000 Hz.

### Changed
- Refactored `KeyboardEvent.code` listener system for zero input delay.
- Optimized canvas matrix rendering for 240Hz+ high refresh rate monitors.

### Fixed
- Fixed key release stuck state bug on Windows OS key combinations (`Win + L`, `Win + D`).
- Fixed media key event capturing on macOS Safari browsers.

---

## [v2.1.0] - 2026-03-10

### Added
- Anti-Ghosting matrix detection tool with multi-key lockup visualization.
- Audio response latency click-test utility.
- Dark mode custom theme options for keyboard visualization.

### Changed
- Enhanced dark high-contrast color scheme for tested keys (Active, Tested, Stuck).
- Improved SEO metadata rendering across all documentation pages.

---

## [v2.0.0] - 2026-01-05

### Added
- Complete platform rebuild with modern HTML5 / Vanilla TypeScript frontend.
- Zero-data-retention client-side key event processing model.
- Support for ChromeOS, macOS, Linux, and Windows default keyboard maps.

---

## [v1.0.0] - 2025-08-20

### Added
- Initial public release of KeyboardTest.tech online testing utility.
- Basic 104-key ANSI layout test.
- Keystroke press and release visual counter.
