# TODO

> Working task sequence for Project Vanguard. This file is intentionally short enough to maintain, but detailed enough to prevent small usability gaps from being forgotten.

The current priority is a properly functioning NixOS/Hyprland workstation environment. Visual identity, lore polish, and immersion work stay secondary until normal desktop use is stable.

---

## Current Priority: Desktop Sanity Baseline

The first big goal is not theme polish. It is a workstation that behaves correctly during ordinary use: launching apps, opening files, copying text, taking screenshots, locking, showing system state, handling audio, and recovering cleanly from small mistakes.

---

### 1. Clipboard history launcher

**Status:** Complete locally.

- `wl-paste --watch cliphist store` starts automatically.
- `SUPER + V` opens the clipboard history picker through Fuzzel.
- `CTRL + V` pastes the selected item after picker selection.
- Local commit: `f73d80a` — `Fix clipboard history picker shortcut`.

---

### 2. Simple status bar

**Status:** Complete locally.

- Waybar starts under Hyprland.
- Initial modules include Hyprland workspaces, clock, network, CPU, memory, and tray.
- Local commit: `4dc5eab` — `Add status bar foundation`.

---

### 3. Notification daemon

**Status:** Complete locally.

- `swaync` / SwayNotificationCenter added as the notification daemon.
- `notify-send` test notification appeared correctly.
- The daemon is suitable for later visual customization.
- Local commit: `f646cfb` — `Add notification daemon foundation`.

---

### 4. Graphical privilege prompt agent

**Status:** Complete locally.

- A graphical privilege prompt agent was added for Hyprland sessions.
- Startup is handled through the generated Hyprland configuration.
- Manual launch stayed running silently, which is expected for this background agent.
- Local commit: `a97ae47` — `Add polkit authentication agent`.

---

### 5. Confirm XDG desktop portals

**Status:** Next.

**Why:** Screen sharing, file pickers, browser integration, and sandboxed applications often rely on XDG desktop portals. Broken portals can make a desktop look fine while quietly breaking basic workflows.

Expected result:

- Hyprland portal support is installed and active.
- File picker behavior works in graphical applications.
- Screen capture or sharing behavior is verified later when needed.

---

### 6. Add basic audio and volume controls

**Status:** Open.

Expected result:

- Audio service is confirmed.
- Volume control utility is installed.
- Practical keybinds or launcher workflow are added.
- Waybar audio display can use the same audio stack.

---

### 7. Add basic display and brightness controls

**Status:** Open.

Expected result:

- Brightness control utility is installed where hardware supports it.
- Display tooling is chosen for Wayland/Hyprland.
- Hardware-specific assumptions are avoided until a target field machine is selected.

---

### 8. Add idle and lock behavior

**Status:** Open.

Expected result:

- Idle detection is configured.
- Screen locks after a sensible delay.
- Display sleep behavior is considered separately from lock behavior.
- The current manual `SUPER + L` lock shortcut remains available.

---

### 9. Add MIME defaults

**Status:** Open.

Expected result:

- Browser default is set.
- File manager default is set for directories.
- Basic defaults exist for text, images, PDFs, and archives.
- Defaults are documented before deeper app choices are made.

---

### 10. Add archive and extraction tools

**Status:** Open.

Expected result:

- Common archive formats can be opened and extracted.
- Nautilus integration is considered if useful.
- Tools remain simple and reproducible.

---

### 11. Add font, icon, and cursor basics

**Status:** Open.

Expected result:

- Basic font package set is selected.
- Icon theme is installed.
- Cursor theme is installed.
- GTK/Qt consistency is considered later, after the baseline is stable.

---

### 12. Improve lock screen appearance

**Status:** Deferred until utility baseline is stable.

Expected result:

- Lock screen is visually coherent.
- Configuration remains simple and reproducible.
- No sensitive or real-world identifiers are used.

---

### 13. Clean and review local NixOS configuration structure

**Status:** Open after the first utility pass.

Expected result:

- Clear separation between system configuration and user configuration.
- Hardware-generated config stays out of public docs.
- Candidate structure identified for a later `vanguard-os` repository.

---

### 14. Update documentation after each confirmed local milestone

**Status:** Ongoing.

Expected result:

- `docs/IMPLEMENTATION_LOG.md` records completed local milestones.
- `docs/ROADMAP.md` reflects current priority.
- `README.md` stays accurate and concise.
- This TODO file is revised when the working order changes.
