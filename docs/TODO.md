# TODO

> Working task sequence for Project Vanguard. This file is intentionally short and should be edited as the system changes.

The current priority is a properly functioning NixOS/Hyprland workstation environment. Visual identity, lore polish, and immersion work stay secondary until normal desktop use is stable.

---

## Current Priority: Functional Workstation Foundation

### 1. Resolve clipboard history launcher

**Status:** Open.

**Why:** Clipboard history is already storing entries through `cliphist`, and the manual picker command works. The `SUPER + V` Hyprland bind does not launch correctly yet. This should be fixed before treating clipboard history as complete.

Expected result:

- `wl-paste --watch cliphist store` starts automatically.
- Clipboard entries are stored across normal copy operations.
- `SUPER + V` opens a picker through Fuzzel.
- Selecting an item copies it back to the active clipboard.

Current known-good manual command:

```sh
cliphist list | fuzzel --dmenu | cliphist decode | wl-copy
```

---

### 2. Add a simple status bar

**Status:** Open.

**Why:** The desktop works, but it has no persistent system information. A basic Waybar setup should show time, battery or power state where relevant, network state, workspace state, and simple system status. This helps make Vanguard usable before it becomes themed.

Expected result:

- Waybar starts with Hyprland.
- Bar content is minimal and readable.
- Configuration remains generic enough to adjust later.

---

### 3. Add basic audio and volume controls

**Status:** Open.

**Why:** A workstation needs reliable sound output and quick volume control before it can be considered comfortable for daily use or demos.

Expected result:

- Audio service confirmed.
- Volume control utility installed.
- Keybinds or launcher workflow added for practical control.

---

### 4. Add basic display and brightness controls

**Status:** Open.

**Why:** The system should support routine screen adjustment before moving toward laptop or field hardware profiles.

Expected result:

- Brightness control utility installed where hardware supports it.
- Display tooling chosen for Wayland/Hyprland.
- Hardware-specific assumptions avoided until a target field machine is selected.

---

### 5. Improve lock screen appearance

**Status:** Deferred until utility baseline is stable.

**Why:** Locking works through `swaylock`, but the default visual style is temporary and does not fit Vanguard. The lock screen should eventually match the project identity, but theming should not interrupt core utility work.

Expected result:

- Lock screen is visually coherent.
- Configuration remains simple and reproducible.
- No secrets, private details, or real-world military identifiers are used.

---

### 6. Clean and review local NixOS configuration structure

**Status:** Open after the first utility pass.

**Why:** The live system is still being built locally in `/etc/nixos`. Before creating a future implementation repository, the configuration should be organized enough to avoid dragging messy experiment history into the public OS codebase.

Expected result:

- Clear separation between system configuration and user configuration.
- No hardware-generated config committed to public docs.
- No secrets, Tailscale auth material, SSH keys, or private network details included.
- Candidate structure identified for a later `vanguard-os` repository.

---

### 7. Update documentation after each confirmed local milestone

**Status:** Ongoing.

**Why:** The GitHub repository is documentation/planning only for now. It should record what has actually been tested locally, not imagined implementation details.

Expected result:

- `docs/IMPLEMENTATION_LOG.md` records completed local milestones.
- `docs/ROADMAP.md` reflects current priority.
- `README.md` stays accurate and concise.
