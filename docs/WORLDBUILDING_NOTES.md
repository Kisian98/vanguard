# Worldbuilding Notes

> Temporary notes for Vanguard's fictional identity and unresolved worldbuilding ideas.

This file is a scratchpad. Stable project boundaries belong in `PROJECT_SCOPE.md`, design rules belong in `docs/DESIGN_PRINCIPLES.md`, implementation planning belongs in `docs/ARCHITECTURE.md`, and milestones belong in `docs/ROADMAP.md`.

---

## Current Fictional Direction

Vanguard OS is developed in-universe by **Vanguard Systems**.

Vanguard Systems is currently imagined as a fictional private contractor focused on field computing products. For now, only Vanguard OS is defined. The company may become a multi-product company later.

Primary in-universe customer direction:

- Military-industrial organizations
- Private security companies

This is fictional branding only. Vanguard does not represent or imply any relationship with real military, security, intelligence, or government organizations.

---

## Product Framing

Vanguard is not only a Hyprland configuration or a NixOS dotfiles concept.

It should be treated as a fictional field workstation platform, with the future NixOS/Hyprland implementation acting as the first reference build of Vanguard OS.

The goal is not to make Linux look tactical. The goal is to build a believable workstation that feels like equipment.

---

## Naming Notes

Current working names:

- Vanguard: overall project/platform identity
- Vanguard OS: operating system product
- Vanguard Systems: fictional company
- Operator: primary user role

Possible subsystem names:

- Atlas: maps and geospatial display
- Relay: communications and networking candidate
- Beacon: node discovery, signal, and presence
- Sentinel: system monitoring and diagnostics
- Archive: documents, notes, manuals, and reference material
- Watchtower: dashboards and public information feeds
- Dispatch: tasking, logs, and operations notes
- Forge: configuration, deployment, and system building

These names are placeholders. Plain technical names should be used when they improve usability. For example, `Configuration` is currently preferred over a fictional name for settings.

---

## AI Notes

The AI operator name is not yet chosen.

Current AI role:

- Copilot
- Expert system
- Knowledge base
- Operations planning assistant
- Obsidian-backed reference and notes

The default tone should be neutral and system-like. A more deliberate assistant personality can be considered later if a Jarvis-like agent becomes useful.

---

## Relationship to Other Projects

Vanguard can interact with other personal infrastructure without becoming dependent on it.

Possible relationship model:

- Hermes: automation and orchestration engine
- Browser-worker: web automation layer
- Vanguard: immersive interface and field workstation

Hermes can be the engine. Vanguard can be the cockpit.

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

Avoid direct imitation of real military systems, official insignia, copyrighted logos, or recognizable government branding.

---

## Current Decisions

- Vanguard Systems is the fictional company name.
- Vanguard OS is the current product focus.
- The system is intended for MilSim, role-play, demonstrations, and technical experimentation.
- The first visible branded layer should likely be a custom GRUB theme.
- Firmware/vendor-logo customization is higher risk and should wait.
- Fiction should be layered on top of the system, not hide how it works.
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
