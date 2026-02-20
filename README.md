# Compaq Portable 486c Restoration

A documentation project tracking the restoration of a Compaq Portable 486c/66 — a luggable 486-era PC with a built-in 10.4" TFT display.

## Machine Specifications

| Component | Details |
|-----------|---------|
| **CPU** | Intel 486DX2-66 MHz |
| **RAM** | 4 MB (original), upgraded to 24 MB |
| **Hard Drive** | 210 MB Conner 3.5" |
| **Expansion** | 2× EISA slots |
| **Floppy** | 3.5" floppy drive |
| **Display** | 10.4" VGA TFT (640×480) |
| **Audio** | AWE64 (added via EISA slot) |
| **Architecture** | Small backplane with CPU card + RAM |

## Restoration Log

### 1. Screen Replacement

The original Sharp LQ10D016 display was damaged beyond repair due to leaking capacitors. A replacement Sharp LQ104V1DG51 was sourced and adapted to work with the proprietary graphics card. This involved building a custom pin adapter cable, constructing a BLANK-to-Data-Enable delay circuit on the video card, and installing a modern CCFL inverter for the backlight.

**[Full screen replacement documentation →](docs/screen-replacement/README.md)**

### 2. PSU Replacement

*Documentation in progress.*

### 3. Processor Upgrade to AMD Am5x86 133 MHz

*Documentation in progress.*

### 4. SCM ISAC2PR10 ISA PCMCIA Adapter

An ISA PCMCIA adapter card (SCM Microsystems ISAC2PR10, Vadem VG-469 chipset) was installed to add dual PC Card slots. This opens up the wide range of 1990s PC Cards — network adapters, flash storage, modems, and SCSI controllers.

**[Full PCMCIA adapter documentation →](docs/pcmcia-adapter/README.md)**

*Documentation in progress.*

## Project Structure

```
compaq-portable-486c-restoration/
├── README.md                            # This file
├── LICENSE
├── CHANGELOG.md
├── docs/
│   ├── screen-replacement/
│   │   ├── README.md                    # Detailed screen replacement guide
│   │   ├── datasheets/
│   │   │   ├── Compaq_Display_Pinout_Mapping.pdf   # Old↔new pin mapping
│   │   │   └── LQ10D011_Datasheet.pdf              # Reference Sharp panel datasheet (closest to original LQ10D016)
│   │   └── images/                      # Restoration photos
│   ├── psu-replacement/
│   │   └── README.md                    # PSU replacement guide
│   ├── cpu-upgrade/
│   │   └── README.md                    # AMD Am5x86 133 MHz upgrade guide
│   ├── pcmcia-adapter/
│   │   └── README.md                    # SCM ISAC2PR10 ISA PCMCIA adapter notes
│   └── images/                          # General project photos
└── .gitignore
```

## Contributing

If you're working on a similar Compaq Portable restoration, feel free to open an issue or pull request with your findings. Community knowledge around these machines is scarce, and every bit helps.

## References

- [VCFed Forum Thread](https://forum.vcfed.org/index.php?threads/compaq-portable-486c-restore-and-upgrade.73098/) — My restoration thread with discussion and community Q&A
- [DOSReloaded Forum Thread (German)](https://dosreloaded.de/forum/thread/7354-compaq-portable-486c-66/?postID=254850#post254850) — Detailed write-up by *Beckenrandschwimmer* covering the display replacement with oscilloscope measurements and circuit design
- [YouTube Demo Video](https://youtu.be/Afo2d6c1wBg) — DOSReloaded restored unit running with new display
- [Compaq Portable 486 Pictures & Firmware (Bitsavers)](http://bitsavers.org/pdf/compaq/Compaq_Portable_486/pictures/) — Reference photos and firmware dumps

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.
