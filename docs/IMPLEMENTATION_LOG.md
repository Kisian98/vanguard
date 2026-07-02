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

---

## 2026-07-02 — Local Flake Foundation

**Status:** Complete.

Confirmed setup:

- Local `flake-conversion` branch created before introducing `flake.nix`.
- Initial `flake.nix` and `flake.lock` created.
- `nix flake show` confirmed `nixosConfigurations.vanguard` exists.
- `nixos-rebuild test --flake .#vanguard` completed successfully.
- `nixos-rebuild switch --flake .#vanguard` completed successfully.
- Local `flake-conversion` branch was fast-forwarded into `master`.
- Temporary local `flake-conversion` branch was removed after merge.
- Local Git tree returned to a clean state.

---

## 2026-07-02 — Home Manager Foundation

**Status:** Complete.

Confirmed setup:

- Local `home-manager-foundation` branch created before editing the flake.
- Home Manager input added to the local flake.
- Minimal `home.nix` created for the `operator` user.
- Home Manager was integrated through the NixOS module path.
- `nix flake show` confirmed the updated flake remained valid.
- `nixos-rebuild test --flake .#vanguard` completed successfully.
- Local `home-manager-foundation` branch was fast-forwarded into `master`.
- Temporary local `home-manager-foundation` branch was removed after merge.
- Local Git tree returned to a clean state.

Important boundary:

The live local NixOS configuration is being versioned on the Vanguard machine first. This repository records the milestone and order of work, but still does not contain the live implementation.

---

## Immediate Next Steps

1. Create a local `hyprland-foundation` branch on the Vanguard machine.
2. Add Hyprland in the smallest viable form.
3. Keep the first Hyprland change focused on proving a basic graphical session can start.
4. Do not start `greetd` or identity/theming work until Hyprland itself is stable.
5. Update this repository again after the Hyprland foundation is tested and merged locally.

---

## Current Build Rule

Until the implementation repository exists, this repository may track decisions, milestones, and architecture notes, but should not contain the live operating system implementation itself.
