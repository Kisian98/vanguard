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

---

## 2026-07-02 — Hyprland Foundation

**Status:** Complete.

Confirmed setup:

- Local `hyprland-foundation` branch created before editing the graphical session configuration.
- System-level Hyprland support enabled through the NixOS configuration.
- Minimal user-level Hyprland configuration added through Home Manager-managed `hyprland.conf`.
- `kitty` added as the first terminal inside the graphical session.
- Basic keybinds tested: open terminal, close active window, and exit Hyprland.
- Norwegian keyboard layout configured for the Hyprland session.
- `nixos-rebuild test --flake .#vanguard` completed successfully.
- Hyprland launched successfully from TTY.
- `nixos-rebuild switch --flake .#vanguard` completed successfully after validation.
- Local `hyprland-foundation` branch was fast-forwarded into `master`.
- Temporary local `hyprland-foundation` branch was removed after merge.
- Local Git tree returned to a clean state.

---

## 2026-07-02 — Greetd Login Foundation

**Status:** Complete.

Confirmed setup:

- Local `greetd-foundation` branch created before editing the login configuration.
- `greetd` enabled as the first login manager foundation.
- `tuigreet` configured as the minimal text-based greeter.
- The greeter command starts the existing Hyprland session.
- `nixos-rebuild build --flake .#vanguard` completed successfully.
- `nixos-rebuild test --flake .#vanguard` activated the greeter successfully.
- Login as `operator` launched Hyprland from the greeter.
- Kitty worked inside the greeter-launched Hyprland session.
- `nixos-rebuild switch --flake .#vanguard` completed successfully after validation.
- Local `greetd-foundation` branch was fast-forwarded into `master`.
- Temporary local `greetd-foundation` branch was removed after merge.
- Local Git tree returned to a clean state.

Important boundary:

The live local NixOS configuration is being versioned on the Vanguard machine first. This repository records the milestone and order of work, but still does not contain the live implementation.

---

## Immediate Next Steps

1. Create a local `desktop-foundation` branch on the Vanguard machine.
2. Add the smallest useful desktop package set.
3. Keep the first desktop change focused on a normal operator workflow inside Hyprland.
4. Do not start identity/theming work until the basic desktop tools are stable.
5. Update this repository again after the desktop foundation is tested and merged locally.

---

## Current Build Rule

Until the implementation repository exists, this repository may track decisions, milestones, and architecture notes, but should not contain the live operating system implementation itself.
