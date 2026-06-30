# Architecture

> Planned architecture for the future **Vanguard OS** implementation. This repository remains documentation-first and does not contain the OS itself.

---

## Repository Boundary

The current `vanguard` repository is the planning and design source of truth.

It may contain:

- Architecture plans
- Design references
- UI concepts
- Roadmaps
- Product identity notes
- Implementation notes for later use

It should not contain:

- Functional NixOS implementation files
- Hardware-generated configuration
- Secrets or private keys
- Deployment credentials
- Large runtime assets

The future implementation repository is expected to be named `vanguard-os`.

---

## Future Repository Purpose

The future `vanguard-os` repository should contain:

- NixOS configuration
- Home Manager configuration
- Hyprland configuration
- Runtime assets
- Scripts
- Installation and deployment logic
- Testing

It should reference this repository as its design and architecture source.

---

## Planned Implementation Layout

The future `vanguard-os` repository may use a layout similar to this:

```text
vanguard-os/
├── flake.nix
├── flake.lock
├── hosts/
│   ├── desktop/
│   └── toughbook/
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

This is a planning reference, not a final commitment.

---

## Planned Layers

### Foundation

The operating system base.

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

Replaceable tools that provide operator functionality.

Examples:

- Browser
- Terminal
- Obsidian
- Mapping tools
- ShadowBroker or similar OSINT tooling
- System utilities
- File manager
- Media tools

### Immersion

Vanguard-specific identity and experience.

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

The immersion layer should reinforce the fictional workstation experience without interfering with normal usability.

---

## Host Profiles

Initial planned profiles:

- `desktop`: development and reference machine
- `toughbook`: field and event deployment machine

The desktop profile should make iteration easy. The Toughbook profile should adapt Vanguard to portable field hardware.

---

## Core Systems vs Tools

Core systems define the platform identity. Tools are integrated applications that can be replaced.

Possible core systems:

- Configuration
- Atlas
- Relay
- Sentinel
- Archive
- Operator AI
- Authentication
- System status

Possible tools:

- Browser
- Terminal
- Obsidian
- ShadowBroker
- System monitors
- File manager
- Media applications

---

## Implementation Principles

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

These commands are illustrative only. Exact implementation details belong in the future `vanguard-os` repository.

---

## Deferred Architecture Topics

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
