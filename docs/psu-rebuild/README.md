# PSU Rebuild — Compaq Portable 486c

## Overview

The original power supply in the Compaq Portable 486c is a common failure point. Aging electrolytic capacitors dry out and lose capacitance, leading to voltage droop, ripple, and eventually failure to start. A full recap restores the PSU to reliable operation.

## Recap

The PSU board was removed from its enclosure and all electrolytic capacitors were replaced. The board was cleaned of any electrolyte residue before installing the new caps.

![PSU board removed and recapped on the workbench](images/01-psu-board-recapped.jpg)

## Voltage Verification

After recapping, the PSU was tested with a multimeter to verify clean output on all rails before reconnecting to the motherboard.

**12V rail** — Reading 12.11V, well within spec.

![Multimeter reading 12.11V on the 12V rail](images/02-12v-rail-test.jpg)

**5V rail** — Reading 5.085V, well within spec.

![Multimeter reading 5.085V on the 5V rail](images/03-5v-rail-test.jpg)

## Reassembly

The rebuilt PSU board reinstalled in its metal enclosure, ready to go back into the case.

![Rebuilt PSU reassembled in its enclosure](images/04-psu-reassembled.jpg)

## Files in This Directory

```
psu-rebuild/
├── README.md                    # This file
└── images/
    ├── 01-psu-board-recapped.jpg  # PSU board after full recap
    ├── 02-12v-rail-test.jpg       # Multimeter showing 12.11V on 12V rail
    ├── 03-5v-rail-test.jpg        # Multimeter showing 5.085V on 5V rail
    └── 04-psu-reassembled.jpg     # Rebuilt PSU back in its enclosure
```
