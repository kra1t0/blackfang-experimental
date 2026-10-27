# BlackFang Experimental - Initial Threat Model

**Status:** Initial working draft  
**Project:** BlackFang Experimental  
**Purpose:** Establish the project's security philosophy and initial threat assumptions.

## 1. Core Philosophy

BlackFang Experimental is a research project exploring a specialized, privacy-focused Linux operating system for privacy enthusiasts and individuals with demanding operational-security requirements.

The system is designed around one guiding principle:

**BlackFang exists to protect the human operating it.**

The operating system should reduce unnecessary exposure, make security-relevant behavior understandable, preserve user agency, and introduce safeguards when user mistakes could cause serious harm.

Privacy and operational security should be built into the system's architecture rather than left entirely to the user's manual configuration.

BlackFang is experimental. Its security properties, limitations, and assumptions must be investigated and tested rather than presumed.

BlackFang experimental has 4 core vectors that's considered to build the philosophy behind the project.

## 2. The Four Vectors

### 2.1 The Human

The human is the primary beneficiary of the system, but humans are fallible. Mistakes, misunderstanding, coercion, and accidental disclosure are relevant risks.

BlackFang should aim to:
- Provide understandable warnings about security-relevant actions.
- Introduce guardrails and, where justified, prevent dangerous operations.
- Make important consequences visible before irreversible actions.
- Preserve user agency without assuming every user decision is informed.

The objective is not to eliminate human error, but to reduce its likelihood and consequences.

### 2.2 The Network

The network and internet service provider are treated as potentially hostile or observable.

BlackFang should investigate:
- Privacy-preserving network routing, including Tor integration.
- Protection against unintended traffic and DNS leaks.
- Controls that prevent applications from bypassing intended routing policies.
- Resistance to browser, protocol, and system fingerprinting.
- Optional proxy configurations with clearly documented limitations.

Anonymity, confidentiality, and fingerprint resistance are distinct objectives. No single mechanism guarantees all three.

### 2.3 The Physical Device

The hardware on which BlackFang runs is not automatically trusted.

The project should investigate:
- Minimizing unnecessary hardware and peripheral access.
- Explicit control over storage mounting and writes.
- Reducing unnecessary background services and device exposure.
- Limitations imposed by firmware, malicious peripherals, compromised hosts, and hardware-level attacks.

A live environment may help avoid relying on the host operating system, but it cannot guarantee that the underlying hardware or firmware is trustworthy.

### 2.4 The Software Supply Chain

Installed software is another potential source of compromise.

BlackFang should investigate:
- A curated software ecosystem suited to its intended use cases.
- Cryptographically verified packages and repository metadata.
- Controlled software installation and updates.
- Application isolation and privilege restrictions.
- Auditable build and release processes.

Software approval does not establish that a package is vulnerability-free. The repository, signing keys, build infrastructure, and update process must also be considered.

## 3. Trust Assumptions

BlackFang begins with the following working assumptions:

- Networks and network intermediaries may monitor, manipulate, or block traffic.
- Hardware and firmware may contain vulnerabilities or be compromised.
- Software may be malicious, vulnerable, or incorrectly configured.
- Humans may make mistakes, including under pressure.
- Security controls may fail and must not be treated as infallible.

These assumptions do not mean that every component is necessarily compromised or that recovery is impossible.

The design objective is to minimize implicit trust, make trust dependencies explicit, isolate failures where practical, and limit their consequences.

## 4. Intended Operating Model

The initial direction is a minimal, Arch-based Linux system designed for privacy-focused and operational-security-sensitive activities.

A live, bootable environment on removable media is the current target direction. Encrypted persistence is a potential future capability.

Virtual-machine support, installation to internal storage, and alternative deployment models remain open decisions.

The target system should contain only the components justified by its intended purpose, while retaining the functionality required for a usable operating environment.

## 5. Scope and Limitations

This document describes design intent, not implemented functionality.

**BlackFang does not yet claim to provide guaranteed anonymity, resistance to all forms of surveillance, protection against compromised firmware, or immunity to sophisticated targeted attacks.**

Security claims must be supported by implementation details, testing, and clearly stated assumptions.

## 6. Open Research Questions

The following questions remain unresolved:

- What adversaries and attack capabilities should the system prioritize?
- How should network routing policies be enforced and verified?
- Which identifying signals can realistically be reduced or standardized?
- What hardware and peripheral access should be permitted by default?
- How should package trust, updates, and recovery be managed?
- What data should persist, and how should persistent state be protected?
- How should users inspect, verify, and recover the system when a component fails?

These questions will be refined as research and implementation progress.

## 7. Guiding Principle

**Protect the human. Minimize trust. Make limitations visible. Verify security claims.**

BlackFang Experimental will develop these principles through incremental implementation, documented decisions, and reproducible testing.
