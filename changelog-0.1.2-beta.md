# Hackboard v0.1.2-beta

## What's New
- **Karabiner-Elements conflict detection** — The installer now checks for an existing Karabiner-Elements installation and blocks with a clear message, preventing conflicts with Hackboard's bundled Hb-Karabiner-Elements. Both the macOS installer UI and the preinstall script enforce this check.
- Fix: Search clear button tap target corrected.

## Notes
- If you have Karabiner-Elements installed, uninstall it before installing Hackboard. Your configuration files in `~/.config/karabiner/` will be preserved. A reboot is needed after uninstalling.
