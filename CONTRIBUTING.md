# Contributing to KeyboardTest.tech Documentation

First off, thank you for considering contributing to the official documentation of **KeyboardTest.tech**! It is community contributions like yours that make KeyboardTest.tech the premiere, authoritative reference for keyboard testing, hardware diagnostics, anti-ghosting engineering, and input latency analysis.

---

## Code of Conduct

This project and everyone participating in it is governed by the [KeyboardTest.tech Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code. Please report unacceptable behavior to `support@keyboardtest.tech`.

---

## How Can I Contribute?

### 1. Improving Existing Documentation
If you spot typos, broken links, outdated technical explanations, or missing SEO frontmatter:
1. Fork the repository.
2. Create a topic branch (`git checkout -b docs/fix-ghosting-diagram-typo`).
3. Make your edits following our Markdown Style Guide.
4. Submit a Pull Request targeting `main`.

### 2. Adding New Guides or FAQ Entries
We welcome new technical guides on emerging keyboard technologies (e.g., Magnetic Switches, Rapid Trigger, SOCD / Snappy Taps, Optical Switches, Custom Firmware like QMK/ZMK/Vial):
1. Open an issue using the **Feature Request** template to propose your topic.
2. Discuss the structure with maintainers.
3. Write the guide inside `docs/` using our standard SEO metadata schema.

---

## Markdown Style & Documentation Conventions

To maintain a trustworthy, enterprise-grade, and SEO-optimized documentation repository, please follow these guidelines:

### SEO Frontmatter Header
Every `.md` file inside `docs/` must begin with an SEO Metadata Block:

```markdown
<!--
SEO Title: [Descriptive, Keyword-Rich Title | KeyboardTest.tech]
Meta Description: [150-160 character meta description containing primary keyphrase]
Primary Keyword: [Target Keyword]
Secondary Keywords: [Comma-separated list of secondary terms]
URL Slug: [docs/slug-name.md]
-->
```

### Writing Tone & Style
- **Developer & Enthusiast Focused:** Concise, precise, authoritative, professional, and clear.
- **No Keyword Stuffing:** Write naturally for humans first while incorporating semantic SEO keywords organically.
- **Heading Hierarchy:** Strictly use `# H1` once per page, followed by `## H2` for primary sections, and `### H3` for subsections.
- **Code & Keys:** Enclose single keys or key combinations in standard markdown code tags (e.g., `Ctrl + Shift + Esc`).

### Relative Internal Linking
Always link internally using relative markdown paths:
- Correct: `[Anti-Ghosting Guide](anti-ghosting.md)` or `[Supported Browsers](../SUPPORTED_BROWSERS.md)`
- Incorrect: Absolute URLs pointing to raw GitHub pages.

---

## Pull Request Submission Process

1. Ensure your Markdown files compile without broken syntax.
2. Run markdown verification if local tools are installed.
3. Fill out the [Pull Request Template](.github/PULL_REQUEST_TEMPLATE.md) completely.
4. Ensure CI validation passes on your PR.

Thank you for helping improve KeyboardTest.tech!
