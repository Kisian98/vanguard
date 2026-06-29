# Roadmap

> This roadmap outlines the planned evolution of Vanguard. It is a living document and should change as the project matures.

---

## Vision

Build a believable fictional field workstation that combines a coherent product identity with a reproducible NixOS implementation.

Vanguard OS is the first reference implementation of the Vanguard platform. In-universe, it is developed by Vanguard Systems, a fictional private contractor focused on field computing products.

Version numbers represent project maturity, not final feature completeness.

---

## Roadmap Principles

The roadmap should follow these principles:

- Build the reproducible base before heavy theming.
- Integrate existing software before creating custom replacements.
- Keep core systems distinct from modular tools.
- Prioritize offline-capable workflows before Internet-reliant features.
- Make each milestone usable, testable, and reviewable.
- Treat version 1.0 as event-ready, not finished.

---

## Core Systems and Tools

Vanguard should separate core systems from replaceable tools.

Core systems are part of the platform identity. They define how Vanguard feels and behaves.

Possible core systems:

- Configuration
- Atlas: maps and geospatial display
- Relay: communications and networking candidate
- Sentinel: system monitoring and diagnostics
- Archive: documents, notes, manuals, and reference material
- Operator AI: copilot, expert system, knowledge base, and planning assistant
- Authentication
- System status

Tools are applications integrated into Vanguard. They can be replaced without changing the identity of the platform.

Possible tools:

- Browser
- Terminal
- Obsidian
- ShadowBroker
- System monitors
- Media tools
- File manager

---

## Version 0.1 — Foundation

**Objective:** Establish the reproducible base system.

- Initial NixOS flake
- Home Manager integration
- Hyprland running
- Basic repository structure
- Development host configuration
- Core documentation
- Git workflow
- First branch and pull request workflow

**Exit criteria:** Vanguard can be built and iterated from the repository on a development machine.

---

## Version 0.2 — Core Platform

**Objective:** Create a stable workstation base.

- Shared Nix modules
- Desktop profile
- Toughbook profile
- Common package set
- Basic Waybar
- Terminal configuration
- Browser
- File manager
- Theme variables
- Core keybinds
- Basic system status

**Exit criteria:** Vanguard works as a normal Hyprland workstation before the immersion layer is added.

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
- Basic animation language
- Failure-state language
- Initial Vanguard Systems branding

**Exit criteria:** The system is clearly recognizable as Vanguard without relying on explanation.

---

## Version 0.4 — Operator Experience

**Objective:** Make the workstation feel purpose-built.

- Mission or operations dashboard
- Status widgets
- System health display
- Maps
- Configuration interface
- Offline-first behavior
- Operator workflow refinement
- Calm warning and error states
- Minimal interaction path for field/event use

**Exit criteria:** The system feels like equipment for an operator, not a themed desktop.

---

## Version 0.5 — Integration

**Objective:** Integrate useful tools into a cohesive platform.

- Obsidian integration
- AI subsystem exploration
- Public data sources
- OSINT tooling research
- ShadowBroker evaluation
- Documentation improvements
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
- Field-oriented power and display defaults

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
- Backup profile or recovery path

**Exit criteria:** Vanguard is ready for a controlled demo without needing constant manual explanation.

---

## Version 1.0 — First Deployment

**Objective:** Vanguard is ready for its first event.

Version 1.0 does not mean the project is finished. It means the workstation is coherent, stable, and presentable enough to be used at a real MilSim or role-play event.

Minimum 1.0 expectations:

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

These are intentionally left for later discussion.

- AI operator name
- AI personality, if a Jarvis-like assistant becomes useful
- Demo mode vs development mode
- Design language details
- Public dashboard implementation
- Wider Vanguard Systems product line
- Optional lore document
- Slogan or tagline
- Whether some engineering or debug screens should intentionally look unfinished
