# Hackboard

![macOS 13+](https://img.shields.io/badge/macOS-13%2B-blue?style=flat-square)
![Karabiner-Elements](https://img.shields.io/badge/Karabiner--Elements-15.0.0-green?style=flat-square)

Hackboard is a macOS app enabling layered keymaps (based on the hold-tap paradigm) to trigger actions more efficiently and ergonomically with your keyboard. **Hold a key, tap another, map it to an action - that's a keymap.**

**Examples**:

| Sequence | Action |
|---|---|
| `Hold ⌘` → `Hold A` → `Tap T` | Open Terminal |
| `Hold ⌘` → `Hold A` → `Hold S` → `Tap M` | Open Maps in Safari |
| `Hold F` → `Tap J, K, L, ;` | Arrow Keys |
| `Hold F` → `Tap Space` | Enter |
| `Hold ⌘` → `Hold T` → `Tap E` | Type your_email@example.com |


Hackboard bundles Hb-Karabiner-Elements, a fork of [Karabiner-Elements](https://karabiner-elements.pqrs.org/) by [Fumihiko Takayama](https://github.com/tekezo) — without his years of work, this wouldn't exist. [Support his work](https://karabiner-elements.pqrs.org/docs/pricing/). Inspired by [Max Stoiber's sublayer concept](https://github.com/mxstbr/karabiner). Fully compatible with your existing Karabiner config, currently pinned to version 15.0.0.

<img src="./demo_recording.gif" width="50%" />

<img src="./demo_image.jpeg" />

## Beta 

Pre-launch users obtain a free lifetime license by submitting feedback through the app (provide email!). A generous free tier and a fair lifetime license will exist after launch. 

## Get Started

1. [Download Latest GitHub Release](https://github.com/farbe-software/hackboard/releases/latest/download/Hackboard.dmg)
2. **Hb-Karabiner-Elements** starts automatically after install — grant the macOS permissions it requests (Input Monitoring, virtual HID driver).
3. **Start Hackboard** — it asks for access to the folder containing `karabiner.json` via a system folder picker.
4. Hackboard loads an example configuration - try it, change it and hack away!

> [!IMPORTANT]
> **Switching from Karabiner-Elements?** Uninstall it first and ensure your `karabiner.json` is compatible with Karabiner-Elements 15.0.0.
> - If there are problems with permissions, try deactivating and reactivating them.
> - Your existing `karabiner.json` rules remain unaffected and will continue to work. If any of them conflict with your Hackboard keymaps, the Hackboard keymaps take priority.

## Uninstall

A full uninstall can be triggered from the Hackboard settings page or through the Hb-Karabiner-Elements UI. Either option removes both applications. A restart is required to complete the uninstallation.

## Feedback & Issues

Found a bug or have a suggestion? [Open an issue](https://github.com/farbe-software/hackboard/issues) on this repository.

## Legal

By downloading and using Hackboard, you agree to the [Terms of Service](TERMS.md) and acknowledge the [Privacy Policy](PRIVACY.md).