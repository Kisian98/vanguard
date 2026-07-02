# Vanguard

> Planning and design repository for a fictional field workstation project.

---

## Overview

Vanguard is a fictional field workstation concept for MilSim, role-play, demonstrations, and technical experimentation.

The project documents the product vision, design direction, roadmap, and planned architecture for **Vanguard OS**. Early bare-metal experimentation has now begun on a dedicated NixOS host, while the operating system implementation itself remains outside this repository until the future `vanguard-os` repository is created.

In-universe, Vanguard OS is developed by **Vanguard Systems**, a fictional private contractor focused on field computing products.

---

## Repository Purpose

This repository is for planning and design first.

It contains:

- Project scope
- Design principles
- Roadmap
- Architecture planning
- Implementation milestone notes
- Worldbuilding notes
- Future implementation guidance

It should not contain the actual operating system implementation, hardware-generated configuration, secrets, deployment credentials, private network details, or large runtime assets.

---

## Current Documents

- `PROJECT_SCOPE.md` — project boundaries, goals, and out-of-scope items
- `docs/DESIGN_PRINCIPLES.md` — design rules and experience principles
- `docs/ROADMAP.md` — planned project milestones
- `docs/ARCHITECTURE.md` — planned future implementation architecture
- `docs/IMPLEMENTATION_LOG.md` — confirmed build milestones and local implementation notes
- `docs/WORLDBUILDING_NOTES.md` — temporary fictional identity notes
- `docs/INSPIRATIONS.md` — reference projects and influence boundaries

---

## Project Status

Vanguard has moved from concept-only planning into the first controlled bare-metal experiment.

Confirmed first host milestone:

- Dedicated NixOS installation for Vanguard experimentation
- Isolated drive and EFI setup
- Existing Fedora and Windows installations left untouched
- Tailscale and OpenSSH enabled for remote administration
- Initial base tools installed, including `fastfetch`

The first implementation repository is still expected to be created later as `vanguard-os` when the local configuration is stable enough to formalize.

---

## License

This project will be released under an open-source license. The specific license will be chosen as the project matures.
