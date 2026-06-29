# Project Scope

# Vanguard

## Overview

Vanguard is a fictional field workstation built on NixOS and Hyprland.

The project aims to create an immersive, near-future command workstation suitable for MilSim, role-play events, demonstrations, and portfolio development. Vanguard is designed to feel believable and cohesive while remaining entirely fictional.

Vanguard should be treated as a fictional product platform. The current NixOS and Hyprland build is the first reference implementation of Vanguard OS, not the entire identity of the project.

The project prioritizes immersion, usability, and technical craftsmanship over visual excess. Every component should serve a purpose, even if that purpose is atmosphere.

---

# Product Identity

In-universe, Vanguard OS is developed by **Vanguard Systems**, a fictional private contractor focused on field computing products.

For now, Vanguard OS is the only defined product. The wider company and product line may be developed later as the fictional setting matures.

The intended in-universe customers are primarily military-industrial organizations and private security companies. Vanguard remains fictional and is not affiliated with any real organization.

---

# Project Goals

- Create a reproducible NixOS configuration.
- Develop a cohesive Hyprland desktop experience.
- Build an immersive field workstation interface.
- Integrate useful public information sources.
- Support optional AI-assisted interaction.
- Remain fully reproducible through Git.
- Be suitable for demonstrations at LAN, MilSim, and role-play events.
- Serve as a practical portfolio project for product identity, UX, documentation, and technical implementation.

---

# Design Principles

Vanguard should be:

- Responsive
- Dependable
- Meaningful
- Actionable
- Functional
- Information-dense
- Easy to maintain
- Modular
- Reproducible

The interface should resemble fictional field equipment built for operators, not a gaming overlay.

---

# AI Philosophy

Artificial intelligence is an optional subsystem.

The AI should function as a copilot, expert system, knowledge base, and planning assistant rather than a general desktop chatbot.

Potential functions include:

- Situation summaries
- Translation
- Equipment reference
- Knowledge lookup
- Navigation assistance
- Operations planning
- Obsidian-backed reference and notes

The AI operator name is not yet chosen. A neutral system-like personality is preferred unless a more deliberate assistant personality becomes useful later.

---

# Public Data Policy

All displayed information should originate from publicly available or user-provided sources.

Examples include:

- Weather
- Maps
- Public transportation
- ADS-B aircraft data
- AIS maritime data
- Public satellite information
- OpenStreetMap
- System information
- User-created content

No restricted or classified information is intended or required.

---

# Architecture Philosophy

Vanguard should integrate existing software before replacing it.

Existing tools should be themed, organized, and presented as part of a coherent workstation when they meet the project's needs. Custom components should be built only when existing software cannot provide the required experience or functionality.

Some systems should become core parts of Vanguard's identity. Most applications should remain modular tools that can be replaced without changing what Vanguard is.

Vanguard should be offline-capable first. Internet access should expand functionality, not be required for the basic workstation experience.

---

# Fictional Setting

Vanguard is a fictional project.

It does not represent, imitate, or claim affiliation with:

- Any military organization
- Any intelligence agency
- Any government
- Any emergency service
- Any law enforcement organization

Branding, terminology, icons, and visual identity should remain original.

The current working direction is a believable private-contractor field computing product, not an official military system.

---

# Project Structure

The project is divided into three layers.

## Foundation

- NixOS
- Flakes
- Home Manager
- Hyprland
- Waybar
- Security
- Networking

## Applications

- Terminal
- Maps
- Notes
- Browser
- Media
- Public dashboards
- Utilities

## Immersion

- Theme
- GRUB theme
- Login screen
- Sound effects
- AI subsystem
- Widgets
- Mission logs
- Status displays

Each layer should remain independently usable.

---

# Out of Scope

The project is not intended to become:

- Offensive security software
- Malware
- Surveillance software
- A military simulation
- A command-and-control platform
- A real intelligence platform
- A replacement for professional mapping or GIS software

---

# Versioning

Vanguard 1.0 means the system is ready to be used at its first event.

It does not mean the project is finished. It means the workstation is coherent, stable, and presentable enough for public use.

Demo builds and early previews should remain below 1.0.

---

# Long-Term Vision

A fully reproducible NixOS workstation that can be installed onto compatible hardware from a single Git repository while preserving the complete Vanguard experience.

The project should be portable, modular, maintainable, and strong enough to stand as a product-design and technical portfolio piece.
