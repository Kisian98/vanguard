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

---

## 2026-07-02 — Desktop Launcher and Browser Foundation

**Status:** Complete.

Confirmed setup:

- Local `desktop-foundation` branch created before editing the desktop package set.
- `fuzzel` added as the first Wayland-native app launcher.
- `SUPER + SPACE` configured as the launcher keybind.
- Vivaldi added as the first graphical browser.
- Existing unfree-package support was reused for Vivaldi.
- `nixos-rebuild build --flake .#vanguard` completed successfully.
- `nixos-rebuild switch --flake .#vanguard` completed successfully after validation.
- Fuzzel opened correctly from the Hyprland keybind.
- Vivaldi launched correctly from Fuzzel.
- Local `desktop-foundation` branch was fast-forwarded into `master`.
- Temporary local `desktop-foundation` branch was removed after merge.
- Local Git tree returned to a clean state.

Important boundary:

The live local NixOS configuration is being versioned on the Vanguard machine first. This repository records the milestone and order of work, but still does not contain the live implementation.

---

## 2026-07-02 — Terminal Comfort and Lock Shortcut

**Status:** Complete.

Confirmed setup:

- Kitty moved from plain package installation into Home Manager's `programs.kitty` configuration.
- Kitty font size increased for easier use inside Hyprland.
- Kitty copy and paste keybindings adjusted so `CTRL + C` copies selected text or interrupts when no text is selected, and `CTRL + V` pastes from clipboard.
- `swaylock` added as the first lock utility.
- `SUPER + L` configured as the desktop lock shortcut.
- `nixos-rebuild build --flake .#vanguard` completed successfully.
- `nixos-rebuild switch --flake .#vanguard` completed successfully after validation.
- Local terminal and lock changes were committed and merged into local `master`.

Known follow-up:

- The current `swaylock` visual style is temporary. A proper Vanguard lock screen theme should be added later, after the core utility baseline is stable.

---

## 2026-07-02 — Desktop Utilities Foundation

**Status:** Complete for file manager, screenshots, and clipboard history foundation.

Confirmed setup:

- Local `desktop-utilities-foundation` branch created before adding desktop utilities.
- Nautilus added as the first file manager.
- Standard user directories added through Home Manager-managed XDG user directories.
- `gvfs` enabled system-wide so Nautilus Trash support works correctly.
- `grim`, `slurp`, and `wl-clipboard` added for Wayland screenshot and clipboard workflows.
- Full-screen screenshot keybind added with `SUPER + Print`.
- Region screenshot keybind added with `SUPER + SHIFT + Print`.
- Screenshot output directory confirmed under the user's Pictures directory.
- `cliphist` added as the clipboard history foundation.
- Clipboard entries are stored correctly.
- The clipboard picker script works manually.
- `SUPER + V` opens the clipboard history picker through Fuzzel.
- Selecting a clipboard history item and then pressing `CTRL + V` pastes the selected item correctly.
- Clipboard picker fix completed locally in commit `f73d80a` — `Fix clipboard history picker shortcut`.
- Local utility branches were fast-forwarded into `master` and removed after merge.
- Local Git tree returned to a clean state.

---

## 2026-07-02 — Status Bar Foundation

**Status:** Complete locally.

Confirmed setup:

- Local `status-bar-foundation` branch created before adding Waybar.
- Waybar added through Home Manager configuration.
- Waybar added to the user package set.
- Hyprland startup configuration now includes `exec-once = waybar`.
- Initial Waybar modules include Hyprland workspaces, clock, network, CPU, memory, and tray.
- `nixos-rebuild build --flake .#vanguard` completed successfully.
- `nixos-rebuild switch --flake .#vanguard` completed successfully after validation.
- Manual `waybar` launch displayed the bar correctly.
- `hyprctl dispatch exec waybar` displayed the bar correctly.
- Generated Hyprland configuration confirmed the Waybar startup line.
- Local `status-bar-foundation` branch was fast-forwarded into `master`.
- Temporary local `status-bar-foundation` branch was removed after merge.
- Local Git tree returned to a clean state.
- Completed in local `/etc/nixos` commit `4dc5eab` — `Add status bar foundation`.

Known follow-up:

- Add a notification daemon.
- Confirm polkit authentication flow.
- Confirm XDG desktop portal behavior.
- Add basic audio and display controls.
- Improve lock screen appearance after utility basics are stable.

---

## Immediate Next Steps

1. Add a notification daemon.
2. Confirm polkit authentication flow.
3. Confirm XDG desktop portal behavior.
4. Add audio and volume control basics.
5. Add basic display and brightness controls.
6. Keep lock screen theming deferred until the utility baseline is stable.
7. Keep updating `docs/TODO.md` as the working sequence changes.

---

## Current Build Rule

Until the implementation repository exists, this repository may track decisions, milestones, and architecture notes, but should not contain the live operating system implementation itself.
