# BlackFang Experimental

**A privacy-focused Linux operating system experiment.**

BlackFang Experimental explores the design and development of a specialized Linux environment for privacy-conscious users and demanding operational-security use cases.

The project investigates how an operating system can minimize implicit trust, reduce unnecessary exposure, enforce understandable security policies, and give users greater control over their computing environment.

BlackFang is not intended to be a general-purpose desktop distribution. Its architecture will be shaped by its threat model and validated through implementation and testing.

## Core Principles

- **Human-first security:** Protect the user's interests while preserving informed control.
- **Minimize trust:** Treat networks, devices, software, and external infrastructure as potentially hostile.
- **Privacy by design:** Integrate privacy considerations into system architecture rather than relying exclusively on user discipline.
- **Explicit limitations:** Document assumptions, trade-offs, and known weaknesses.
- **Verifiable claims:** Test security properties rather than treating design intentions as proof.

## Development

BlackFang is in an early experimental stage. Development currently focuses on establishing the engineering foundation and investigating the architecture required for a minimal, privacy-oriented Linux system.

The project uses Arch Linux as its starting point for research and system construction. The development environment is separate from the intended BlackFang target system.

No guarantees of complete anonymity, resistance to all surveillance, or protection against every targeted attack are currently claimed.

## Documentation

- [Threat Model](docs/threat-model.md) — Security objectives, trust assumptions, scope, and open research questions.
- [Development Log](docs/dev-log.md) — Implementation progress, technical decisions, and session notes.

## Status

**Experimental — active development.**

Features, architecture, and security controls remain subject to change. Security properties will be documented as they are implemented and tested.

## Guiding Principle

> Protect the human. Minimize trust. Make limitations visible. Verify security claims.
