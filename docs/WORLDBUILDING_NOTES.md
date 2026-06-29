# Worldbuilding Notes

> Temporary notes for Vanguard's fictional identity, interface language, and implementation direction.

These notes are not permanent project doctrine. They exist to capture ideas while the project is still forming. Strong ideas can later be moved into dedicated design documents, architecture notes, or implementation plans.

---

## Core Idea

Vanguard is not only a Hyprland configuration or a NixOS dotfiles repository.

It should be treated as a fictional field workstation platform, with the current NixOS and Hyprland implementation acting as the first reference build of Vanguard OS.

The goal is not to make Linux look tactical. The goal is to build a believable fictional workstation for MilSim, role-play, demonstrations, and technical experimentation.

---

## Vanguard Systems

Vanguard OS is developed in-universe by **Vanguard Systems**.

Vanguard Systems is currently imagined as a fictional private contractor focused on field computing products. For now, only Vanguard OS is defined. The company may eventually have a wider product line, but that should come later as the setting matures.

Current in-universe customer direction:

- Military-industrial organizations
- Private security companies
- Other field-oriented organizations, if useful later

This is fictional branding only. Vanguard does not represent or imply any relationship with real military, security, intelligence, or government organizations.

---

## Reference Implementation

The repository can be understood as the current reference implementation of Vanguard OS.

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

## Core Systems vs Tools

Vanguard should distinguish between core systems and modular tools.

Core systems are part of the Vanguard identity. Changing them changes how Vanguard feels.

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

- Firefox or another browser
- Obsidian
- ShadowBroker
- Kitty or another terminal
- btop or other system monitors
- Image viewer
- Media tools

Existing software should be integrated before custom replacements are built. Custom components should be created when existing tools do not meet the project's functional or aesthetic needs.

---

## Fictional Subsystems

Possible internal subsystem names:

- Vanguard: overall platform
- Vanguard OS: operating system identity
- Atlas: maps and geospatial display
- Relay: communications and networking candidate
- Beacon: node discovery, signal, and presence
- Sentinel: system monitoring and diagnostics
- Archive: documents, notes, manuals, and reference material
- Watchtower: dashboards and public information feeds
- Dispatch: tasking, logs, and operations notes
- Forge: configuration, deployment, and system building

These names are placeholders. Keep, rename, or discard them as the project develops. Fictional names are useful where they add identity. Plain technical names are better when clarity matters.

---

## Interface Philosophy

The interface should feel like equipment, not decoration.

Good Vanguard UI should be:

- Responsive
- Dependable
- Meaningful
- Actionable
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

Current direction:

- Copilot
- Expert system
- Knowledge base
- Operations planning assistant
- Obsidian-backed reference and notes

Possible functions:

- Situation summary
- Translation
- Equipment reference
- Field notes
- Navigation assistance
- Public data lookup
- System explanation
- Operations planning

The AI operator name is not yet chosen. A neutral, system-like personality is preferred by default. A more deliberate assistant personality can be considered later if a Jarvis-like agent becomes useful.

---

## Offline and Online Behavior

Vanguard should be offline-capable first.

The core workstation should remain useful without Internet access. Internet access should expand capabilities through tools such as public dashboards, maps, OSINT sources, and live information feeds.

The main intended use still assumes the machine can be connected to the Internet when needed.

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

## Versioning

Vanguard 1.0 means the system is ready to be used at its first event.

It does not mean the project is finished. It means the workstation is coherent, stable, and presentable enough for public use.

Demo builds and early previews should remain below 1.0.

---

## Current Decisions

- Fictional company name: Vanguard Systems.
- Current product focus: Vanguard OS.
- Vanguard Systems may become a multi-product company later.
- Primary in-universe customers: military-industrial organizations and private security companies.
- Primary user role: operator.
- The AI operator name is not yet chosen.
- AI role: copilot, expert system, knowledge base, and planning assistant.
- Subsystems may use fictional names, but plain technical names are acceptable when they improve usability.
- Configuration is preferred over a fictional name for settings.
- Network is clear, though Relay remains a possible subsystem name.
- The first visible branded layer should likely be a custom GRUB theme. Firmware/vendor-logo customization can be considered later, but is higher risk and hardware-specific.
- Fiction should be sprinkled on top. Vanguard remains NixOS with Hyprland underneath.
- Custom sound design should be used only where it matters.
- Existing software should be integrated before custom replacements are built.
- Offline capability should come before Internet-reliant tools.
- Vanguard 1.0 means event-ready, not finished.

---

## Deferred Design Topics

- AI operator name.
- Whether the AI should eventually have a deliberate personality.
- Whether some engineering/debug screens should intentionally look unfinished.
- Whether the Toughbook build needs separate layouts beyond hardware-specific settings.
- Whether the interface should support event/demo mode separate from development mode.
- How public OSINT dashboards should be embedded, linked, or recreated as local UI modules.
- Design language: typography, spacing, animation, icon style, borders, and color system.
- Slogan or tagline.
- Optional lore document.
- Wider Vanguard Systems product line.

---

## Temporary Status

This file is a scratchpad.

Move stable ideas into formal documents later, such as:

- `docs/DESIGN_GUIDELINES.md`
- `docs/ARCHITECTURE.md`
- `docs/UI_CONCEPTS.md`
- `docs/AI_SUBSYSTEM.md`
- `docs/ROADMAP.md`
