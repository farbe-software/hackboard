# Hackboard - Security Information

Thank you for helping us keep Hackboard secure.

## Permissions

Hackboard customizes keyboard input at the system level. This requires privileges:

- **Input Monitoring** — Hb-Karabiner-Elements sees all keyboard input system-wide. This is how key remapping works; no keystroke data is stored or transmitted.
- **Virtual HID driver** — A signed DriverKit extension (from pqrs, the Karabiner maintainer) creates a virtual keyboard that delivers remapped input to macOS.
- **Root background service** — `karabiner_grabber` runs with root privileges to access low-level input devices. This is standard for keyboard customization tools on macOS and inherited unchanged from Karabiner Elements.
- **Shell commands** — Keymaps can trigger shell commands that run as your user account. You author all configurations yourself; Hackboard does not support importing third-party configs.


## Security Model

**Local-first.** Hackboard operates entirely on your machine. All keyboard input is processed locally by Karabiner's virtual keyboard driver — no keystrokes, usage patterns, or personal data are intentionally transmitted from your machine. All configurations are created and modified by you alone; Hackboard does not include functionality to import third-party configurations. You carry full control and responsibility for your setup.

**Inherited security architecture.** Hb-Karabiner-Elements does not modify the Karabiner Elements security model. The root-privileged core service, virtual HID driver restrictions, and closed-process design are inherited unchanged from upstream. For details, see the [Karabiner Elements security documentation](https://karabiner-elements.pqrs.org/docs/help/advanced-topics/security/).

**File access.** Hackboard requests access to the folder containing `karabiner.json` via a macOS system folder picker. It uses security-scoped bookmarks to remember this access across launches, and cannot read or write files outside the granted folder without explicit user consent.

**Minimal network activity.** Hackboard's only network communication:
- **Update checks** — When automatic update checks are enabled, Sparkle periodically fetches a small XML file from this repository to check for new versions. You can also check for updates manually via the menu. Your IP address is transmitted to GitHub Pages as part of the request.
- **Crash reports** — When crash reporting is enabled in Settings, crash data is sent to Sentry if the app encounters an error. Crash reports may incidentally contain technical identifiers; personally identifiable information is not intentionally collected (`sendDefaultPii: false`). See [Privacy Policy](PRIVACY.md) for details.

## Inherent Risks

Keyboard involves risks that are inseparable from the technology:

- **Elevated system privileges** — Root-level processes (`karabiner_grabber`, `Karabiner-VirtualHIDDevice-Daemon`, `karabiner_session_monitor`) run with system access to intercept keyboard input at the hardware level.
- **Shell command execution** — Keymaps can trigger arbitrary shell commands. Maliciously or inadvertantly configured commands can perform harmful actions. 
- **Unexpected keyboard behavior** — Misconfigured keymaps may cause keys to produce unintended input, stop responding, or behave erratically.
- **Software conflicts** — Other software that modifies keyboard input may conflict with Hackboard. Hackboard cannot coexist with a separate Karabiner-Elements installation.

Hackboard actively mitigates each of these risks through its security architecture, configuration validation, and command safety filtering.

### Installed System Components

Hackboard consists of the Hackboard app (the Flutter GUI) and Hb-Karabiner-Elements (a customized fork of the open-source [Karabiner Elements](https://karabiner-elements.pqrs.org/)). The bulk of the system-level footprint comes from Hb-Karabiner-Elements, whose security architecture is inherited unchanged from the established upstream project.

**Hackboard app:**

| Component | Location |
|-----------|----------|
| Hackboard.app | /Applications/ |
| User preferences and state | ~/Library/Application Support/com.farbe.hackboard/ |
| `hb_keymaps.json` (keymap config) | ~/Library/Application Support/com.farbe.hackboard/ |

**Hb-Karabiner-Elements** (all components below originate from the Karabiner Elements open-source project):

*Applications:*

| Component | Location |
|-----------|----------|
| Hb-Karabiner-Elements.app | /Applications/ |
| Karabiner-EventViewer.app | /Applications/ |
| Karabiner-Menu.app | /Library/Application Support/org.pqrs/ |
| Karabiner-NotificationWindow.app | /Library/Application Support/org.pqrs/ |
| Karabiner-MultitouchExtension.app | /Library/Application Support/org.pqrs/ |

*Root-level services (LaunchDaemons):*

| Service | Purpose |
|---------|---------|
| `karabiner_grabber` | Low-level keyboard event capture (runs as root) |
| `Karabiner-VirtualHIDDevice-Daemon` | Virtual HID device management (runs as root) |

*User-level services (LaunchAgents):*

| Service | Purpose |
|---------|---------|
| `karabiner_console_user_server` | IPC server, shell command execution |
| `karabiner_session_monitor` | Session state monitoring (setuid root) |
| `karabiner_grabber` (user agent) | User-level event capture |
| `Karabiner-Menu` | Menu bar UI |
| `Karabiner-NotificationWindow` | System notifications |
| `Karabiner-MultitouchExtension` | Trackpad event support |

*Other:*

| Component | Details |
|-----------|---------|
| DriverKit extension | Karabiner-DriverKit-VirtualHIDDevice (user-space virtual HID driver, signed by pqrs) |
| setuid binary | `karabiner_session_monitor` (4755) — required for `CGSessionCopyCurrentDictionary` |
| Configuration | `~/.config/karabiner/karabiner.json` (permissions 0600) |

**Uninstall:** The bundled uninstaller removes all system components listed above. User configuration (`karabiner.json`, Hackboard preferences) is preserved for manual deletion.



## Reporting a Vulnerability

If you discover a security vulnerability in Hackboard or Hb-Karabiner-Elements, please report it responsibly.

**Email:** [contact@hackboard.app](mailto:contact@hackboard.app)

Please include:
- A description of the vulnerability and its potential impact
- Steps to reproduce, if possible
- The version of Hackboard and macOS you are using
- If the vulnerability extends to upstream Karabiner-Elements, consider reporting there as well.

We will acknowledge your report within 7 days and work with you to understand and address the issue. Please do not disclose the vulnerability publicly until we have had a reasonable opportunity to fix it. For information on how we handle your personal data, see our [Privacy Policy](PRIVACY.md).

## Scope

This policy covers:
- **Hackboard** (the macOS app)
- **Hb-Karabiner-Elements** (the bundled Karabiner fork)
