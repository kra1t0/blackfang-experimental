# BlackFang Experimental - Development Log

## Session 01: Development Environment Setup

**Date:** 2026-10-27  
**Status:** Development environment installed; initial setup complete.

### Objective

Establish a minimal Arch Linux virtual machine as the development workbench for BlackFang Experimental.

The VM is a workspace for development and testing. It is not the target BlackFang operating system, and the goal is not to customize this installed Arch system into the final product.

### Environment

- **Hypervisor:** VirtualBox
- **Guest OS:** Arch Linux
- **Firmware:** UEFI
- **Virtual disk:** 30 GiB, dynamically allocated VDI
- **Memory:** 4096 MiB
- **Processors:** 3 virtual CPUs
- **Networking:** NAT
- **Installation mode:** Minimal, console-oriented

### Disk Layout

The virtual disk `/dev/sda` was initialized with a GPT partition table.

| Partition | Size | Type | Purpose |
|---|---:|---|---|
| `/dev/sda1` | 512 MiB | EFI System | UEFI boot files |
| `/dev/sda2` | ~29.5 GiB | Linux filesystem | Root filesystem |

The EFI partition was formatted as FAT32, and the root partition as ext4. The root filesystem was mounted at `/mnt`, with the EFI partition mounted at `/mnt/boot` during installation.

### Installation

The base system was installed using `pacstrap`, including:

- `base`
- `linux`
- `linux-firmware`
- `grub`
- `efibootmgr`
- `networkmanager`
- `sudo`
- `git`
- `nano` (ofcourse)

The filesystem table was generated with `genfstab`. System configuration was performed inside `arch-chroot`.

### Initial Configuration

- Timezone set to `Asia/Colombo`.
- Hardware clock synchronized.
- Hostname set to `blackfang-dev`.
- Local host mappings configured.
- GRUB installed for `x86_64-efi`.
- GRUB configuration generated.
- NetworkManager enabled for startup.
- Root password configured.

Package signature verification encountered issues during installation, which were resolved sufficiently to continue.

### Current State

- The Arch installation completed without errors in the final configuration steps.
- Networking was confirmed working.
- The environment is intended to be accessed through the console.
- No desktop environment was installed.

### Decisions and Boundaries

1. The development VM is separate from the BlackFang target system.
2. The target OS will be built and tested as a separate system image rather than by stripping down this VM.
3. The workbench should remain minimal and serve the project's engineering needs.
4. Security properties of the eventual target must be justified by the threat model and verified through testing; the workbench configuration alone establishes no such guarantees.

---

*This log records the initial development setup. It is an interim record and may be revised as the implementation and architecture evolve.(Or a personal document that states what I did so I can later revisit and follow the same principal)*
