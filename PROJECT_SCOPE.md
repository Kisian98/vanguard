# Project Scope

## Purpose

Vanguard is a fictional field workstation project centered on product identity, user experience, and a future reproducible NixOS/Hyprland implementation.

This repository is the planning and design source of truth. It does not contain the operating system implementation itself.

---

## Product Identity

Vanguard OS is the first planned product in the Vanguard platform.

In-universe, it is developed by **Vanguard Systems**, a fictional private contractor focused on field computing products. The wider company and product ecosystem may be developed later.

The current fictional customer direction is military-industrial organizations and private security companies. This is fictional context only. Vanguard does not represent, imitate, or claim affiliation with any real organization.

---

## Project Goals

- Define a believable fictional field workstation.
- Establish a coherent product identity and design language.
- Plan a future NixOS/Hyprland implementation.
- Keep the future implementation modular, reproducible, and maintainable.
- Integrate useful public or user-provided information sources.
- Support optional AI-assisted workflows without making AI required for normal use.
- Prepare the project to become a practical portfolio piece.

---

## Experience Goals

Vanguard should feel like dependable field equipment for an operator.

It should be:

- Responsive
- Dependable
- Meaningful
- Actionable
- Functional
- Information-dense
- Fictional without copying real-world military systems

Further design rules live in `docs/DESIGN_PRINCIPLES.md`.

---

## Architecture Direction

The future implementation should prioritize:

- Reproducibility from Git
- Separation between shared and hardware-specific configuration
- Offline-capable workflows before Internet-reliant tools
- Existing software integration before custom replacements
- A clear distinction between core systems and replaceable tools

Detailed implementation planning lives in `docs/ARCHITECTURE.md`.

---

## Public Data Policy

All displayed information should originate from public or user-provided sources.

Examples include weather, maps, public transport, ADS-B aircraft data, AIS maritime data, OpenStreetMap, system information, and user-created material.

No restricted or classified information is intended or required.

---

## Out of Scope

Vanguard is not intended to become:

- Offensive security software
- Malware
- Surveillance software
- A military simulation
- A command-and-control platform
- A real intelligence platform
- A replacement for professional mapping or GIS software

---

## Versioning

Vanguard 1.0 means the system is ready to be used at its first event.

It does not mean the project is finished. It means the workstation is coherent, stable, and presentable enough for public use.

Demo builds and early previews should remain below 1.0.
