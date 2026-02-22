# Hackboard

Hackboard is a keyboard customization app for macOS. It enables namespaced shortcut systems by turning letter keys into modifiers (like ⌘, ⌥, ⌃, ⇧). It is driven by a custom fork (called Hb-Karabiner-Elements) of [Karabiner Elements](https://karabiner-elements.pqrs.org/), the trusted open-source tool for keyboard customization on macOS, with a visual editor on top.

## Beta

Hackboard is in public beta. You may encounter rough edges. 

Hackboard needs some system privilidges and allows for security-sensitive configurations. Please refer to the security information at [SECURITY.md](SECURITY.md). Use at your own risk. 

Your feedback is what shapes the product — please [report bugs and share ideas](https://github.com/farbe-software/hackboard-releases/issues). 

## Capabilities

- **Standard modifier + letter key chains**
  <br><small>E.g. holding Left Command, then holding `A` (for 'Application'), then pressing and releasing `T` (for 'Terminal') maps to the shell command 'open -a 'Terminal.app'. This will open the app, or switch to it, if it is open. Standard modifiers and letter-key modifiers work together seamlessly. At least four letter keys can be chained (subject to hardware limitations on some machines).</small>
- **Letter keys as standalone modifiers**
  <br><small>E.g. holding `A`, then pressing and releasing `T` maps to an action, e.g. 'Open Terminal'. No prior modifier needed. Hackboard's built-in rollover behaviour enables standalone letter keys to act as modifiers without interfering with normal typing.</small>
- **Use of right modifiers with separate mapping**
  <br><small>Typically unused right modifiers become useful and help make your keyboard more ergonomic.</small>
- **Triggering of actions**
  <br><small>Actions include shell commands, remapped standard shortcuts in any app, text insertion and simple key-to-key mapping (great for remapping hard-to-reach to more ergonomic alternatives). We will add more action types, including direct integrations (manual shortcut remaping is already possible for any app) with third-party apps, soon.</small>

## Get Started

### Requirements

- macOS 13 (Ventura) or later (earlier versions may work but are not actively supported). 
- Apple Silicon (Intel builds may work but not actively supported)

### Install

*Karabiner-Elements Users: Uninstall first and make karabiner.json compatible with Karabiner-Elements 15.0.0. If you're coming from an older version, you may benefit from migration instructions in the Hb-Karabiner-Elements UI. Downgrading from newer versions will need to done manually.* 

Download the latest `.dmg` from the [Releases page](https://github.com/farbe-software/hackboard-releases/releases/latest) and open the installer package inside it. The installer includes both Hackboard and Hb-Karabiner-Elements — no separate Karabiner download is needed.

### First Launch

After installation completes, **Hb-Karabiner-Elements** starts automatically and requests the necessary macOS permissions (Input Monitoring and a virtual HID driver approval). Follow the dialogs in the Hb-Karabiner-Elements UI until it no longer shows messages for missing permissions.

Note that the HID driver bundled with Hb-Karabiner-Elements is a signed build from pqrs.

*For Karabiner-Elements users: If there are problems, try deactivating and reactivating permissions.*

Once permissions are granted, **start Hackboard**. On launch, Hackboard runs an initial sanity check and asks for access to the folder containing `karabiner.json` via a system folder picker. This is required because Hackboard is sandboxed — it cannot access files outside its sandbox without explicit user consent.

Once folder access is granted, Hackboard loads an example configuration showcasing its capabilities. 

You can then add your first own keymaps through the sidebar, or edit and delete existing ones.

*For Karabiner-Elements users:*  
*The configuration is injected into your `karabiner.json` as follows.*

- *Hackboard writes into the **first profile** in your karabiner.json*
- *It creates a single entry in `complex_modifications.rules` with the description `"hackboard"`*
- *All layer definitions are stored as manipulators of type `"layer"` inside that rule*
- *Only the Hackboard rule is touched — all other rules, profiles, and settings remain unchanged* 

## Config Examples

### A-layer: Applications (with sublayers)

| Hold | Then press | Action |
|------|------------|--------|
| `A` | `C` | Open or Switch to Chrome |
| `A` `C` | `M` | Open Google Maps in Chrome |
| `A` `C` `M` | `K` | Open Google Maps in Chrome in a Specific Location|
| `A` | `F` | Open Finder |
| `A` `F` | `D` | Open Downloads folder |

### Arrow Actions (move/select/delete, vim-inspired)

#### F-layer: Move Cursor / Use Arrow Keys 

Hold `F` for moving the cursor / arrow keys, `S` and `D` for corresponding select and delete actions. The arrow keys are mapped to `J` `K` `L` `;` on the home row — inspired by vim's `hjkl`. Hit enter (on `Space`) and escape (on `A`) without stretching your pinky. 

| Hold | Then press | Action |
|------|------------|--------|
| `F` | `J` | Move cursor left |
| `F` | `K` | Move cursor down |
| `F` | `L` | Move cursor up |
| `F` | `;` | Move cursor right |
| `F` | `U` | Move cursor one word left |
| `F` | `P` | Move cursor one word right |
| `F` | `H` | Move cursor to line start |
| `F` | `'` | Move cursor to line end |
| `F` | `Space` | Enter |
| `F` | `A` | Escape |

Tap `F` by itself and it types "f" as usual.

#### S-layer: Selection 

Hold `S` to select text / items. Uses the same spatial layout as the F-layer, so the muscle memory carries over.

| Hold | Then press | Action |
|------|------------|--------|
| `S` | `J` | Select left |
| `S` | `K` | Select down |
| `S` | `L` | Select up |
| `S` | `;` | Select right |
| `S` | `U` | Select one word left |
| `S` | `P` | Select one word right |
| `S` | `H` | Select to line start |
| `S` | `'` | Select to line end |
| `S` | `F` | Select entire line |
| `S` | `A` | Select all |

### D-layer: Delete

Hold `D` to delete. Same spatial layout again — learn one, know all three.

| Hold | Then press | Action |
|------|------------|--------|
| `D` | `J` | Delete character left (Backspace) |
| `D` | `;` | Delete character right (Forward Delete) |
| `D` | `U` | Delete word left |
| `D` | `P` | Delete word right |
| `D` | `H` | Delete to line start |
| `D` | `'` | Delete to line end |
| `D` | `F` | Delete entire line |

### Number Row on Home Row

Hold Right Command to type numbers from the home row, eliminating the reach to the number row.

| Hold | Then press | Result |
|------|------------|--------|
| `Right ⌘` | `A` | 1 |
| `Right ⌘` | `S` | 2 |
| `Right ⌘` | `D` | 3 |
| `Right ⌘` | `F` | 4 |
| `Right ⌘` | `G` | 5 |
| `Right ⌘` | `H` | 6 |
| `Right ⌘` | `J` | 7 |
| `Right ⌘` | `K` | 8 |
| `Right ⌘` | `L` | 9 |
| `Right ⌘` | `;` | 0 |

## Feedback & Issues

Found a bug or have a suggestion? [Open an issue](https://github.com/farbe-software/hackboard-releases/issues) on this repository.