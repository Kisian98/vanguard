# TODO

> Working task sequence for Project Vanguard. This file is intentionally short enough to maintain, but detailed enough to prevent small usability gaps from being forgotten.

The current priority is a properly functioning NixOS/Hyprland workstation environment. Visual identity, lore polish, and immersion work stay secondary until normal desktop use is stable.

---

## Current Priority: Desktop Sanity Baseline

The first big goal is not theme polish. It is a workstation that behaves correctly during ordinary use: launching apps, opening files, copying text, taking screenshots, locking, showing system state, handling audio, and recovering cleanly from small mistakes.

---

### 1. Resolve clipboard history launcher

**Status:** Open.

**Why:** Clipboard history is already storing entries through `cliphist`, and the manual picker command works. The `SUPER + V` Hyprland bind does not launch correctly yet. This should be fixed before treating clipboard history as complete.

Expected result:

- `wl-paste --watch cliphist store` starts automatically.
- Clipboard entries are stored across normal copy operations.
- `SUPER + V` opens a picker through Fuzzel or another reliable launcher.
- Selecting an item copies it back to the active clipboard.

Current known-good manual command:

```sh
cliphist list | fuzzel --dmenu | cliphist decode | wl-copy
```

---

### 2. Add a simple status bar

**Status:** Open.

**Why:** The desktop works, but it has no persistent system information. A basic Waybar setup should show time, workspace state, network state, audio level, battery or power state where relevant, and simple system status.

Expected result:

- Waybar starts with Hyprland.
- Bar content is minimal and readable.
- Configuration remains generic enough to adjust later.
- No heavy Vanguard theming yet.

---

### 3. Add a notification daemon

**Status:** Open.

**Why:** Many desktop tools rely on notifications for useful feedback. Without a notification daemon, failures and confirmations can disappear silently, which is a stupid way for a computer to be mysterious.

Expected result:

- A Wayland-friendly notification daemon is installed and launched with Hyprland.
- Test notification appears correctly.
- Styling remains basic until the visual identity phase.

---

### 4. Confirm polkit authentication flow

**Status:** Open.

**Why:** Graphical administration tasks often need an authentication prompt. If no polkit agent is available, GUI tools may fail without giving a useful reason.

Expected result:

- A polkit agent is installed or confirmed active.
- GUI privilege prompts work when needed.
- The chosen agent is simple and compatible with the Hyprland session.

---

### 5. Confirm XDG desktop portals

**Status:** Open.

**Why:** Screen sharing, file pickers, browser integration, and sandboxed applications often rely on XDG desktop portals. Broken portals can make a desktop look fine while quietly breaking basic workflows.

Expected result:

- Hyprland portal support is installed and active.
- File picker behavior works in graphical applications.
- Screen capture or sharing behavior is verified later when needed.

---

### 6. Add basic audio and volume controls

**Status:** Open.

**Why:** A workstation needs reliable sound output and quick volume control before it can be considered comfortable for daily use or demos.

Expected result:

- Audio service is confirmed.
- Volume control utility is installed.
- Practical keybinds or launcher workflow are added.
- Waybar audio display can use the same audio stack.

---

### 7. Add basic display and brightness controls

**Status:** Open.

**Why:** The system should support routine screen adjustment before moving toward laptop or field hardware profiles.

Expected result:

- Brightness control utility is installed where hardware supports it.
- Display tooling is chosen for Wayland/Hyprland.
- Hardware-specific assumptions are avoided until a target field machine is selected.

---

### 8. Add idle and lock behavior

**Status:** Open.

**Why:** Manual lock works through `SUPER + L`, but the system should also lock after inactivity. A workstation should not depend on perfect human memory. Humans are not that product line.

Expected result:

- Idle detection is configured.
- Screen locks after a sensible delay.
- Display sleep behavior is considered separately from lock behavior.
- The current manual `SUPER + L` lock shortcut remains available.

---

### 9. Add MIME defaults

**Status:** Open.

**Why:** Opening files should not feel like a small court case. The system needs sensible defaults for browser links, directories, text files, images, PDFs, and archives.

Expected result:

- Browser default is set.
- File manager default is set for directories.
- Basic defaults exist for text, images, PDFs, and archives.
- Defaults are documented before deeper app choices are made.

---

### 10. Add archive and extraction tools

**Status:** Open.

**Why:** Normal desktop use includes opening compressed files. Missing archive support is one of those tiny omissions that becomes annoying instantly.

Expected result:

- Common archive formats can be opened and extracted.
- Nautilus integration is considered if useful.
- Tools remain simple and reproducible.

---

### 11. Add font, icon, and cursor basics

**Status:** Open.

**Why:** Before full theming, the desktop still needs readable fonts, consistent icons, and a usable cursor. This is utility polish, not identity work.

Expected result:

- Basic font package set is selected.
- Icon theme is installed.
- Cursor theme is installed.
- GTK/Qt consistency is considered later, after the baseline is stable.

---

### 12. Improve lock screen appearance

**Status:** Deferred until utility baseline is stable.

**Why:** Locking works through `swaylock`, but the default visual style is temporary and does not fit Vanguard. The lock screen should eventually match the project identity, but theming should not interrupt core utility work.

Expected result:

- Lock screen is visually coherent.
- Configuration remains simple and reproducible.
- No secrets, private details, or real-world military identifiers are used.

---

### 13. Clean and review local NixOS configuration structure

**Status:** Open after the first utility pass.

**Why:** The live system is still being built locally in `/etc/nixos`. Before creating a future implementation repository, the configuration should be organized enough to avoid dragging messy experiment history into the public OS codebase.

Expected result:

- Clear separation between system configuration and user configuration.
- No hardware-generated config committed to public docs.
- No secrets, Tailscale auth material, SSH keys, or private network details included.
- Candidate structure identified for a later `vanguard-os` repository.

---

### 14. Update documentation after each confirmed local milestone

**Status:** Ongoing.

**Why:** The GitHub repository is documentation/planning only for now. It should record what has actually been tested locally, not imagined implementation details.

Expected result:

- `docs/IMPLEMENTATION_LOG.md` records completed local milestones.
- `docs/ROADMAP.md` reflects current priority.
- `README.md` stays accurate and concise.
- This TODO file is revised when the working order changes.
