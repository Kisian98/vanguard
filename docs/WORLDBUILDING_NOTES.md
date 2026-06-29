# Worldbuilding Notes

> Temporary notes for Vanguard's fictional identity, interface language, and implementation direction.

These notes are not permanent project doctrine. They exist to capture ideas while the project is still forming. Strong ideas can later be moved into dedicated design documents, architecture notes, or implementation plans.

---

## Core Idea

Vanguard is not only a Hyprland configuration or a NixOS dotfiles repository.

It should be treated as a fictional field workstation platform, with the current NixOS and Hyprland implementation acting as the first reference build.

The goal is not to make Linux look tactical. The goal is to build a believable fictional workstation for MilSim, role-play, demonstrations, and technical experimentation.

---

## Reference Implementation

The repository can be understood as the current reference implementation of Vanguard.

Potential future implementations could include:

- NixOS workstation edition
- Toughbook field edition
- Desktop command-center edition
- Handheld or tablet companion
- Web dashboard
- Raspberry Pi field display
- Hardware control panel
- Alternative desktop environment edition

The identity of Vanguard should remain separate from any single technical stack.

---

## Fictional Subsystems

Possible internal subsystem names:

- Vanguard: overall platform
- Nix: onboard AI operator candidate
- Atlas: maps and geospatial display
- Relay: communications and networking
- Beacon: node discovery, signal, and presence
- Sentinel: system monitoring and diagnostics
- Archive: documents, notes, manuals, and reference material
- Watchtower: dashboards and public information feeds
- Dispatch: tasking, logs, and mission notes
- Forge: configuration, deployment, and system building

These names are placeholders. Keep, rename, or discard them as the project develops. Fictional names are useful where they add identity. Plain technical names are better when clarity matters.

---

## Interface Philosophy

The interface should feel like equipment, not decoration.

Good Vanguard UI should be:

- Functional first
- Visually restrained
- Information-dense
- Readable outdoors or in low light
- Consistent across modules
- Fictional without copying real-world military software
- Immersive without becoming annoying to use

Avoid turning the project into a normal Linux desktop with tactical wallpaper.

---

## Feature Categories

Every feature should fit at least one of these categories.

### Operational

Provides useful information or control.

Examples:

- Battery
- Network
- VPN
- Weather
- Location
- Maps
- System health
- Time

### Immersive

Reinforces the fictional field workstation experience.

Examples:

- GRUB theme
- Mission log
- AI status
- System initialization messages
- Themed launcher
- Sound cues

### Technical

Improves reproducibility, maintainability, or portability.

Examples:

- Nix modules
- Home Manager structure
- Deployment scripts
- Host profiles
- Theme variables
- Documentation

If a feature does not fit one of these categories, it probably does not belong.

---

## AI Direction

The AI should not be exposed as a general-purpose chatbot by default.

It should behave like an onboard subsystem with constrained functions.

Possible functions:

- Mission brief
- Situation summary
- Translation
- Equipment reference
- Field notes
- Navigation assistance
- Public data lookup
- System explanation

The underlying model or agent can change. The user-facing role should remain consistent.

---

## Relationship to Other Projects

Vanguard can interact with other personal infrastructure without becoming dependent on it.

Possible relationship model:

- Hermes: automation and orchestration engine
- Browser-worker: web automation layer
- Vanguard: immersive interface and field workstation

Hermes can be the engine. Vanguard can be the cockpit.

These projects should remain independently useful.

---

## Visual Influences

Useful inspiration sources:

- Public OSINT dashboards
- Industrial control interfaces
- Rugged field equipment
- Aviation and maritime displays
- Emergency operations dashboards
- Sci-fi command interfaces
- Terminal-based workflows
- Real diagnostic software

The project should avoid direct imitation of real military systems, official insignia, copyrighted logos, or recognizable government branding.

---

## Current Decisions

- The system name should be either Vanguard or Vanguard OS.
- The primary user role is operator.
- The AI operator name is not yet chosen.
- Subsystems may use fictional names, but plain technical names are acceptable when they improve usability.
- The first visible branded layer should likely be a custom GRUB theme. Firmware/vendor-logo customization can be considered later, but is higher risk and hardware-specific.
- Fiction should be sprinkled on top. Vanguard remains NixOS with Hyprland underneath.
- Custom sound design should be used only where it matters.
- The current fictional direction leans toward a private-contractor field computing product.

---

## Open Questions

- Should the system primarily present itself as Vanguard or Vanguard OS?
- What should the AI operator be named?
- Should the Toughbook build have a distinct field profile beyond hardware-specific settings?
- Should the interface support an event/demo mode separate from development mode?
- Should public OSINT dashboards be embedded, linked, or recreated as local UI modules?
- Should lore remain implied through interface design for now, or should a small lore document be created later?
- What kind of fictional private contractor built Vanguard, and what values would that organization have?
- What problem does Vanguard solve inside its fictional world?
- What should the first five minutes of using Vanguard feel like?

---

## Temporary Status

This file is a scratchpad.

Move stable ideas into formal documents later, such as:

- `docs/DESIGN_GUIDELINES.md`
- `docs/ARCHITECTURE.md`
- `docs/UI_CONCEPTS.md`
- `docs/AI_SUBSYSTEM.md`
- `docs/ROADMAP.md`
