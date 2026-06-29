# Design Principles

Vanguard is a fictional field workstation platform. It should feel like dependable equipment, not a decorative desktop theme.

## Core Qualities

Vanguard should be:

- Responsive
- Dependable
- Meaningful
- Actionable

These qualities should guide interface design, system behavior, documentation, and naming.

## Operator First

The primary user is an operator.

The interface can be compact and information-dense, but it must remain understandable. Fictional terminology is allowed when it improves the experience. Plain technical names are better when they make the system easier to use.

## Function Before Atmosphere

Every interface element should have a purpose.

A component should either:

- provide useful information,
- support an action,
- improve system clarity,
- or reinforce the fictional workstation experience.

If it does none of these, it probably does not belong.

## Core Systems vs Tools

Core systems are part of Vanguard's identity. Tools are applications integrated into Vanguard.

A core system should be designed carefully and remain consistent across the workstation. A tool can be replaced when a better option appears.

This keeps Vanguard flexible without making its identity depend on every bundled application.

## Integrate Before Rebuilding

Vanguard should use existing software when it already solves the problem.

Custom components should be created when existing tools cannot provide the required function, integration, or experience.

## Offline First, Online Enhanced

The workstation should remain useful without Internet access.

Internet access should expand functionality through maps, dashboards, OSINT sources, and live feeds. It should not be required for the basic workstation experience.

## Fiction as a Layer

Vanguard is still NixOS with Hyprland underneath.

Fiction should add identity and immersion. It should not hide how the system works, block normal operation, or make the workstation harder to understand.

## Calm Failure States

Problems should be presented clearly and calmly.

Example:

```text
RELAY
LINK LOST
Attempting reconnect...
```

Avoid unnecessary drama. The system should feel reliable even when something fails.

## Sound With Restraint

Sound should be used only for meaningful state changes.

Good uses:

- boot complete
- authentication accepted
- link connected
- warning
- critical failure

Avoid sounds for routine UI noise such as window focus, hover effects, or ordinary clicks.

## Product Mindset

Vanguard should be approached as a fictional product platform and portfolio project.

The current NixOS and Hyprland implementation is the first reference build of Vanguard OS. Future work may include additional profiles, interfaces, dashboards, hardware targets, or companion tools.

## Version 1.0

Vanguard 1.0 means event-ready.

It does not mean finished. It means the system is coherent, stable, and presentable enough to be used at its first event.
