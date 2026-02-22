# Security Policy

Thank you for helping us keep Hackboard secure.

## Security Model

**Local-first.** Hackboard operates entirely on your machine. All keyboard input is processed locally by Karabiner's virtual keyboard driver — no keystrokes, usage patterns, or personal data leave your machine. All configurations are created and modified by you alone; Hackboard does not include functionality to import third-party configurations. You carry full control and responsibility for your setup.

**Inherited security architecture.** Hb-Karabiner-Elements does not modify the Karabiner Elements security model. The root-privileged core service, virtual HID driver restrictions, and closed-process design are inherited unchanged from upstream. For details, see the [Karabiner Elements security documentation](https://karabiner-elements.pqrs.org/docs/help/advanced-topics/security/).

**Sandboxed app.** Hackboard itself runs in the macOS app sandbox. It cannot access files outside its container without explicit user consent via the system folder picker.

**Minimal network activity.** Hackboard's only network communication:
- **Update checks** — Sparkle periodically fetches a small XML file from this repository to check for new versions.
- **Crash reports** — Anonymous crash data is sent to Sentry when the app encounters an error. Personally identifiable information is disabled (`sendDefaultPii: false`).

## Permissions

Hackboard customizes keyboard input at the system level. This requires privileges that go beyond what most apps need:

- **Input Monitoring** — Hb-Karabiner-Elements sees all keyboard input system-wide. This is how key remapping works; no keystroke data is stored or transmitted.
- **Virtual HID driver** — A signed DriverKit extension (from pqrs, the Karabiner maintainer) creates a virtual keyboard that delivers remapped input to macOS.
- **Root background service** — `karabiner_grabber` runs with root privileges to access low-level input devices. This is standard for keyboard customization tools on macOS and inherited unchanged from Karabiner Elements.
- **Shell commands** — Keymaps can trigger shell commands that run as your user account. You author all configurations yourself; Hackboard does not support importing third-party configs.


## Reporting a Vulnerability

If you discover a security vulnerability in Hackboard or Hb-Karabiner-Elements, please report it responsibly.

**Email:** [contact@hackboard.app](mailto:contact@hackboard.app)

Please include:
- A description of the vulnerability and its potential impact
- Steps to reproduce, if possible
- The version of Hackboard and macOS you are using
- If the vulnerability extends to upstream Karabiner-Elements, consider reporting there as well. 

We will acknowledge your report within 7 days and work with you to understand and address the issue. Please do not disclose the vulnerability publicly until we have had a reasonable opportunity to fix it.

## Scope

This policy covers:
- **Hackboard** (the macOS app)
- **Hb-Karabiner-Elements** (the bundled Karabiner fork)

For vulnerabilities in upstream Karabiner Elements, please report them directly to the [Karabiner Elements project](https://github.com/pqrs-org/Karabiner-Elements).
