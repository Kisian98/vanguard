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

## Immediate Next Steps

1. Put `/etc/nixos` under local Git on the Vanguard machine.
2. Keep the local NixOS configuration recoverable before larger changes.
3. Create the future `vanguard-os` implementation repository when the local base is stable enough to formalize.
4. Convert the configuration to flakes.
5. Add Home Manager.
6. Enable Hyprland.
7. Configure `greetd` as the login foundation.
8. Begin Vanguard identity work only after the base system is reproducible.

---

## Current Build Rule

Until the implementation repository exists, this repository may track decisions, milestones, and architecture notes, but should not contain the live operating system implementation itself.
