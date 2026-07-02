# Implementation Log

> Practical build notes for early Vanguard OS host work.

This log records confirmed build decisions and milestones while keeping this repository documentation-first. Do not store generated hardware configuration, secrets, deployment credentials, private keys, Tailscale auth material, or machine-specific sensitive details here.

---

## 2026-07-02 — First Bare-Metal Vanguard Host

**Status:** Initial standalone Vanguard OS host installed and bootable.

The first practical Vanguard OS environment has been created using NixOS on a dedicated experimental drive. This marks the transition from concept-only planning to controlled bare-metal experimentation.

Confirmed setup:

- NixOS installed on a dedicated 1 TB HDD for Vanguard experimentation.
- Existing Fedora and Windows installations left untouched.
- NixOS uses its own EFI partition and `systemd-boot` loader.
- Fedora GRUB remains the main boot menu and includes a custom `Vanguard OS (NixOS)` entry.
- The Vanguard system can be booted from the existing themed GRUB menu.
- Primary local operator account: `operator`.
- Tailscale and OpenSSH enabled for remote administration.
- Initial base tools added: `git`, `vim`, `wget`, `curl`, `nano`, and `fastfetch`.

Local-only items intentionally not committed here:

- `/etc/nixos/hardware-configuration.nix`
- Generated machine-specific NixOS configuration
- Tailscale identity, auth material, or private network details
- SSH keys or credentials

---

## 2026-07-02 — Local Configuration Baseline

**Status:** Local `/etc/nixos` history established.

Confirmed setup:

- `/etc/nixos` initialized as a local Git repository.
- Initial system configuration committed as the recoverable base.
- Local `.gitignore` added for Nix build outputs, editor files, and scratch files.
- Flakes support enabled through `nix.settings.experimental-features`.
- Local `flake-conversion` branch created before introducing `flake.nix`.
- Initial `flake.nix` and `flake.lock` created.
- `nix flake show` confirmed `nixosConfigurations.vanguard` exists.
- `nixos-rebuild test --flake .#vanguard` completed successfully.

Important boundary:

The live local NixOS configuration is being versioned on the Vanguard machine first. This repository records the milestone and order of work, but still does not contain the live implementation.

---

## Immediate Next Steps

1. Run `nixos-rebuild switch --flake .#vanguard` locally to make the flake workflow permanent.
2. Verify the local Git tree is clean after the flake-based switch.
3. Merge the local `flake-conversion` branch back into `master` on the Vanguard machine.
4. Continue with Home Manager.
5. Enable Hyprland only after Home Manager and the flake base are stable.
6. Configure `greetd` as the login foundation.
7. Begin Vanguard identity work only after the base system is reproducible.

---

## Current Build Rule

Until the implementation repository exists, this repository may track decisions, milestones, and architecture notes, but should not contain the live operating system implementation itself.
