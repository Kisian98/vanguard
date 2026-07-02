# Roadmap

> Planned evolution of Vanguard. This is a living document and should change as the project matures.

---

## Vision

Build a believable fictional field workstation that combines a coherent product identity with a future reproducible NixOS/Hyprland implementation.

Version numbers represent project maturity, not final feature completeness.

---

## Roadmap Principles

- Build the reproducible base before heavy theming.
- Integrate existing software before creating custom replacements.
- Keep core systems distinct from modular tools.
- Prioritize offline-capable workflows before Internet-reliant features.
- Make each milestone usable, testable, and reviewable.
- Treat version 1.0 as event-ready, not finished.

Detailed architecture planning lives in `docs/ARCHITECTURE.md`.

---

## Version 0.0 — First Brick

**Objective:** Move from concept-only planning to a controlled bare-metal experiment.

Completed:

- Installed NixOS on a dedicated Vanguard experiment drive.
- Kept Fedora and Windows isolated from the Vanguard installation.
- Confirmed NixOS boots through its own EFI partition and `systemd-boot`.
- Enabled Tailscale and OpenSSH for remote administration.
- Added first base tools: `git`, `vim`, `wget`, `curl`, `nano`, and `fastfetch`.

**Exit criteria:** Vanguard can boot cleanly and be administered remotely for early system work.

**Status:** Complete.

---

## Version 0.1 — Foundation

**Objective:** Establish the reproducible base system.

Completed:

- Local `/etc/nixos` Git history.
- Local `.gitignore` for build outputs and scratch files.
- Flakes support enabled in the existing NixOS configuration.
- Initial `flake.nix` and `flake.lock`.
- Flake test rebuild with `.#vanguard`.
- Permanent flake switch.
- Local `flake-conversion` branch merged back into `master`.
- Home Manager integration.

Remaining:

1. Hyprland running.
2. Development host configuration cleanup.
3. Basic repository structure for the future implementation repository.
4. Core documentation sync.

Current next action:

- Start the local `hyprland-foundation` branch.

**Exit criteria:** Vanguard can be built and iterated from a flake-based local configuration, then moved into the future implementation repository when stable enough.

---

## Version 0.2 — Core Platform

**Objective:** Create a stable workstation base before the immersion layer.

- Shared Nix modules
- Desktop profile
- Toughbook profile
- Common package set
- Basic Waybar
- Terminal, browser, and file manager
- Theme variables
- Core keybinds
- Basic system status

**Exit criteria:** Vanguard works as a normal Hyprland workstation before the immersive layer is added.

---

## Version 0.3 — Vanguard Identity

**Objective:** Establish the visual and interaction language.

- GRUB theme
- Login screen
- Wallpaper system
- Color palette
- Typography
- Icons
- Window styling
- Audio cues
- Failure-state language
- Initial Vanguard Systems branding

**Exit criteria:** The system is recognizable as Vanguard without relying on explanation.

---

## Version 0.4 — Operator Experience

**Objective:** Make the workstation feel purpose-built.

- Operations dashboard
- Status widgets
- System health display
- Maps
- Configuration interface
- Offline-first behavior
- Operator workflow refinement
- Calm warning and error states

**Exit criteria:** The system feels like equipment for an operator, not a themed desktop.

---

## Version 0.5 — Integration

**Objective:** Integrate useful tools into a cohesive platform.

- Obsidian integration
- AI subsystem exploration
- Public data sources
- OSINT tooling research
- ShadowBroker evaluation
- Tool launcher or access pattern
- Local reference material

**Exit criteria:** External tools feel like they belong inside Vanguard rather than being unrelated applications.

---

## Version 0.6 — Field Profile

**Objective:** Optimize Vanguard for portable hardware.

- Toughbook-specific configuration
- Battery optimization
- Touchscreen support
- Display scaling
- Hardware-specific keybinds
- Offline resource packs
- Network fallback behavior

**Exit criteria:** Vanguard can be deployed to the Toughbook as a credible field workstation profile.

---

## Version 0.7 — Event Preparation

**Objective:** Prepare Vanguard for public demonstration.

- Demo stability
- UX polish
- Bug fixes
- Presentation flow
- Documentation cleanup
- Event checklist
- Known failure recovery steps

**Exit criteria:** Vanguard is ready for a controlled demo without constant manual explanation.

---

## Version 1.0 — First Deployment

**Objective:** Vanguard is ready for its first event.

Version 1.0 does not mean finished. It means the workstation is coherent, stable, and presentable enough to be used at a real MilSim or role-play event.

Minimum expectations:

- Reproducible install path
- Stable desktop session
- Cohesive Vanguard identity
- Working field profile
- Clear operator workflow
- Offline-capable baseline
- Event-ready documentation
- No major immersion-breaking rough edges during normal use

---

## Deferred Topics

- AI operator name
- AI personality, if a Jarvis-like assistant becomes useful
- Demo mode vs development mode
- Design language details
- Public dashboard implementation
- Wider Vanguard Systems product line
- Optional lore document
- Slogan or tagline
- Intentional engineering/debug-screen aesthetic
