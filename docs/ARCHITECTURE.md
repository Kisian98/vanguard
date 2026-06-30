# Architecture

> This document describes the planned architecture of the future **Vanguard OS** implementation. The current repository is documentation-first and serves as the project's planning and design reference.

---

## Purpose

The `vanguard` repository is not intended to contain the operating system implementation itself.

Instead, this repository serves as the source of truth for:

- Product vision
- Project scope
- Design principles
- Architecture planning
- User experience
- Worldbuilding
- Roadmaps
- Future implementation decisions

When development begins, the functional implementation should move into a separate repository.

---

## Repository Strategy

### Current Repository

**Repository:** `vanguard`

Purpose:

- Planning
- Documentation
- Design
- Product identity
- Architecture
- UI concepts
- Roadmaps

This repository should remain implementation-agnostic wherever possible.

### Future Repository

**Planned repository:** `vanguard-os`

Purpose:

- NixOS configuration
- Home Manager configuration
- Hyprland configuration
- Assets
- Scripts
- Installation
- Deployment
- Testing

The implementation repository should reference this repository as its architectural and design source.

---

## Planned Implementation Layout

The future `vanguard-os` repository may use a layout similar to this:

```text
vanguard-os/
├── flake.nix
├── flake.lock
├── hosts/
│   ├── desktop/
│   │   ├── configuration.nix
│   │   └── hardware-configuration.nix
│   └── toughbook/
│       ├── configuration.nix
│       └── hardware-configuration.nix
├── modules/
│   ├── core/
│   ├── desktop/
│   ├── hardware/
│   ├── networking/
│   ├── security/
│   └── vanguard/
├── home/
│   ├── kristian.nix
│   └── modules/
├── assets/
│   ├── wallpapers/
│   ├── icons/
│   ├── sounds/
│   └── grub/
├── scripts/
└── docs/
```

This structure is a planning reference, not a final commitment. It should be adjusted when implementation work begins.

---

## Planned Layer Architecture

The future implementation should be divided into distinct layers.

### Foundation

Responsible for the operating system itself.

Examples:

- NixOS
- Flakes
- Home Manager
- Hyprland
- Networking
- Security
- Boot
- Users
- Audio
- Fonts
- Core packages

The foundation layer must remain usable even if the immersion layer is incomplete or disabled.

### Applications

Provides operator functionality.

Examples:

- Browser
- Terminal
- Obsidian
- Mapping tools
- ShadowBroker or similar OSINT tooling
- System utilities
- File manager
- Media tools

Applications should remain replaceable whenever practical.

### Immersion

Responsible for Vanguard's identity.

Examples:

- GRUB theme
- Wallpapers
- Login experience
- Audio cues
- Branding
- Waybar styling
- Status displays
- Interface language
- Calm failure states

This layer should reinforce the fictional workstation experience without interfering with normal usability.

---

## Host Profiles

The implementation is expected to support multiple hardware profiles.

Initial planned profiles:

- `desktop`: development and reference machine
- `toughbook`: field and event deployment machine

The desktop profile should make iteration easy. The Toughbook profile should adapt Vanguard to portable field hardware.

Additional profiles may be introduced later if required.

---

## Core Systems vs Tools

Vanguard should distinguish between core systems and modular tools.

Core systems define the platform identity. Changing them changes how Vanguard feels and behaves.

Possible core systems:

- Configuration
- Atlas: maps and geospatial display
- Relay: communications and networking candidate
- Sentinel: system monitoring and diagnostics
- Archive: documents, notes, manuals, and reference material
- Operator AI: copilot, expert system, knowledge base, and planning assistant
- Authentication
- System status

Tools are integrated applications. Replacing a tool should not change Vanguard's identity.

Possible tools:

- Browser
- Terminal
- Obsidian
- ShadowBroker
- System monitors
- File manager
- Media applications

---

## Implementation Philosophy

The future implementation should follow these principles:

- Reproducible from Git
- Modular by default
- Offline-capable first
- Online-enhanced when available
- Integrate existing software before creating custom replacements
- Separate hardware-specific configuration from shared functionality
- Keep the foundation usable without the immersion layer
- Keep secrets and private credentials out of the repository

---

## Planned Deployment Direction

The intended deployment model is a flake-based NixOS workflow.

Example future commands:

```bash
sudo nixos-rebuild switch --flake .#desktop
```

```bash
sudo nixos-rebuild switch --flake .#toughbook
```

These commands are illustrative only. The exact implementation will be decided in the future `vanguard-os` repository.

---

## Current Repository Boundary

This planning repository should not contain:

- Functional NixOS implementation files
- Hardware-specific generated configuration
- Secrets
- Private keys
- Real deployment credentials
- Large binary assets intended for runtime use

It may contain:

- Architecture plans
- Design references
- UI concepts
- Roadmaps
- Product identity notes
- Planning documents
- Implementation notes for later use

---

## Deferred Architecture Topics

The following topics should be addressed when the implementation repository is created:

- Final module structure
- Package selection
- Theme implementation
- AI runtime
- OSINT integration
- Installation process
- CI/CD
- Hardware-specific optimization
- Release process
- Asset packaging
- Testing strategy
