# QNAP Research Toolkit

[English](README.md) | [Español](README.es.md)

Unofficial toolkit for advanced QNAP diagnostics, recovery and forensic analysis.

> [!WARNING]
> This project contains low-level and experimental tools intended for experienced
> users, controlled laboratories and authorized technical research. Incorrect use
> may cause data loss, service interruption, network failure, firmware corruption
> or an unbootable system.

## Overview

QNAP Research Toolkit is a collection of scripts, utilities, technical notes and
reproducible procedures for studying QNAP NAS systems.

The project focuses on hardware inspection, low-level diagnostics, boot analysis,
storage and network troubleshooting, forensic evidence collection and recovery
workflows.

This is an independent community project. It is not developed, maintained,
supported, sponsored or endorsed by QNAP Systems, Inc.

## Scope

The repository may include material related to:

- Hardware inventory and forensic profiling
- BIOS, UEFI, CSM, BBS and NVRAM analysis
- Boot-device and boot-order inspection
- PCI and PCI Express device analysis
- EEPROM, NVM and option-ROM inspection
- Network-adapter diagnostics and recovery research
- Storage, iSCSI, iSER and SCSI target diagnostics
- Kernel-module analysis and compatibility testing
- QTS service inspection and troubleshooting
- Log collection and technical support bundles
- Controlled recovery and rollback procedures

## Repository structure

```text
qnap-research-toolkit/
├── docs/                 Technical documentation and procedures
├── scripts/              Shell scripts and automation
├── tools/                Diagnostic and analysis utilities
├── profiles/             Sanitized hardware and system profiles
├── examples/             Example configurations and outputs
├── templates/            Templates for new tools and scripts
├── LICENSES/             License texts and licensing guidance
├── .gitattributes
├── .gitignore
├── LICENSE
├── README.md
├── README.es.md
└── THIRD_PARTY_NOTICES.md
```

The structure may evolve as new research areas and tools are added.

## Requirements

Requirements vary by tool. A component may require:

- SSH access to the NAS
- Administrator privileges
- QTS shell access
- Bash or a compatible POSIX shell
- Standard Linux command-line utilities
- Development tools or matching kernel headers
- External recovery media
- A verified backup of configuration and data

Each tool must document its own dependencies, supported systems and expected
side effects.

## Installation

Clone the repository:

```bash
git clone https://github.com/grisno/qnap-research-toolkit.git
cd qnap-research-toolkit
```

Review the source and documentation before executing a tool:

```bash
find . -maxdepth 3 -type f | sort
```

Grant execute permission only when required:

```bash
chmod +x scripts/example-tool.sh
```

Display the tool help or run its inspection mode first:

```bash
./scripts/example-tool.sh --help
```

## Safety principles

Tools in this repository should follow these principles:

1. Operate read-only by default whenever practical.
2. Require explicit confirmation before destructive or persistent changes.
3. Create and verify backups before modifying configuration, firmware or NVRAM.
4. Validate the target model, platform and device identifiers.
5. Record actions, inputs, outputs and return codes.
6. Provide a rollback or recovery procedure where possible.
7. Separate stable, experimental and destructive operations clearly.
8. Avoid redistributing proprietary firmware or vendor binaries.

## Compatibility

A tool working on one QNAP model does not guarantee compatibility with another
model, hardware revision, QTS release, kernel build or boot configuration.

Before use, verify at least:

```text
QNAP model
QTS version and build
Kernel version
CPU architecture
Boot mode
Installed hardware
PCI and device identifiers
Target storage or network interface
```

## Tool maturity

Each tool should declare one of these maturity levels:

| Status | Meaning |
|---|---|
| `stable` | Repeatedly tested on the documented target environment |
| `testing` | Functional but still undergoing validation |
| `experimental` | Research code with limited validation |
| `dangerous` | May modify firmware, NVRAM, storage metadata or hardware state |

A status label is not a warranty. Always review the source and prepare a
recovery path.

## Sensitive information

Before publishing reports or logs, remove or replace:

- Passwords, tokens and session cookies
- Private keys and certificates
- Public IP addresses when disclosure is unnecessary
- MAC addresses when they identify a private environment
- Serial numbers, UUIDs and chassis identifiers
- Hostnames, usernames and organization names
- Storage contents and customer data

Sanitized examples should retain only the information required to reproduce or
understand the technical behavior.

## Proprietary components

This repository does not grant permission to redistribute proprietary QNAP,
AMI, Intel, NVIDIA Networking/Mellanox, Broadcom or other vendor components.

Firmware images, BIOS dumps, option ROMs, EEPROM contents, vendor utilities and
binary drivers remain subject to their respective licenses and ownership
rights.

Whenever possible, tools should require users to provide or extract their own
authorized copy instead of embedding proprietary material.

## Third-party code

Third-party files retain their original copyright notices and licenses.

Files copied from or derived from the Linux kernel, QNAP kernel sources or
another GPL-2.0-only project must preserve their original license. They are not
automatically relicensed under GPLv3.

Use a per-file SPDX identifier where practical:

```text
SPDX-License-Identifier: GPL-3.0-or-later
```

Kernel-derived files may instead require:

```text
SPDX-License-Identifier: GPL-2.0-only
```

The original license and the identifier declared in each file take precedence
for that file. See [LICENSES/README.md](LICENSES/README.md) and
[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

## Contributing

Contributions should include:

- A clear technical description
- Supported QNAP models and QTS versions
- Reproduction or validation steps
- Safety checks and expected changes
- Rollback instructions
- Sanitized example output
- The correct SPDX license identifier

Do not submit secrets, personal data, unauthorized proprietary firmware or
confidential vendor material.

## Disclaimer

This software is provided without warranty.

The authors and contributors are not responsible for data loss, hardware
damage, service interruption, security issues or any other consequences
resulting from use of this project.

Use these tools only on systems that you own or are explicitly authorized to
inspect, test or repair.

## License

Unless otherwise stated in a file, original project code is licensed under the
GNU General Public License, version 3 or any later version:

```text
GPL-3.0-or-later
```

Third-party components and derived works retain their respective licenses. See
the root [LICENSE](LICENSE), the per-file SPDX identifiers and the
[LICENSES](LICENSES/) directory.

## Trademark notice

QNAP and related product names are trademarks or registered trademarks of QNAP
Systems, Inc. Other names may be trademarks of their respective owners.

This independent project is not affiliated with, sponsored by or endorsed by
QNAP Systems, Inc.
