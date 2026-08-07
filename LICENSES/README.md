# Licensing guide

The default license for original project code is:

```text
GPL-3.0-or-later
```

Use this SPDX identifier in original scripts and source files:

```text
SPDX-License-Identifier: GPL-3.0-or-later
```

## Kernel-derived code

Linux kernel code and files derived from GPL-2.0-only sources must preserve the
original license, normally:

```text
SPDX-License-Identifier: GPL-2.0-only
```

Do not relicense copied or modified kernel code as GPL-3.0-or-later.

## Third-party files

Third-party files retain their original licenses. Record them in
`THIRD_PARTY_NOTICES.md` and preserve all required notices.

## Proprietary material

Do not apply the project license to firmware, BIOS images, EEPROM contents,
vendor utilities or other proprietary files. The project license covers the
project's original code, not external material processed by the tools.
