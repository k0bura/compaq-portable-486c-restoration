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

### 1. PSU Rebuild

First step was to rebuild the PSU — it worked but stank like leaking capacitors. Without a stable power supply, any other restoration work would be unreliable. I can replace capacitors here and there, but I don't trust myself enough to do the whole thing with confidence.

I outsourced rebuilding my PSU to [GiGaBiTe](https://forum.vcfed.org/index.php?members/gigabite.35162/) on the Vintage Computer Federation Forums. They did a great job and the power rails are rock stable. The bridge rectifier and all electrolytic capacitors were replaced, along with the DPST power switch and a new cooling fan.

**[Full PSU rebuild documentation →](docs/psu-rebuild/README.md)**

### 2. Screen Replacement

The original Sharp LQ10D016 display was damaged beyond repair due to leaking capacitors. This is very common with these. A replacement Sharp LQ104V1DG51 was sourced and adapted to work with the proprietary graphics card. This involved building a custom pin adapter cable, constructing a BLANK-to-Data-Enable delay circuit on the video card, and installing a modern CCFL inverter for the backlight.

**[Full screen replacement documentation →](docs/screen-replacement/README.md)**

### 3. Keyboard Restoration

The keycaps had the typical vintage yellowing from UV-degraded ABS plastic. I retrobrighted them using the heat method — simmering the keycaps in SalonCare 40 Volume Creme Developer (12% hydrogen peroxide) on the stove at low heat. Heat replaces UV light as the catalyst and provides more even results since all surfaces are submerged. Credit to [The 8-Bit Guy](https://www.youtube.com/@The8BitGuy) as my source for the technique.

The keyboard cable is a very proprietary connector and becomes brittle with age. Mine was damaged but still usable after taping it up. A custom coiled replacement cable is planned.

**[Full keyboard restoration documentation →](docs/keyboard-restoration/README.md)**

## Beyond Restoration

### Processor Upgrade to AMD Am5x86-P75

The original IBM Blue Lightning DX2-66 was replaced with an **AMD Am5x86-P75** (AMD-X5-133ADZ), a drop-in Socket 3 upgrade that delivers Pentium-75 equivalent performance at 133 MHz. The ADZ variant was chosen for its 85°C maximum case temperature rating — critical for this compact case where only a passive heatsink fits. The Compaq has no clock multiplier jumper, so pin R17 (CLKMUL) on the CPU had to be manually grounded to enable the 4x multiplier and reach full 133 MHz speed.

**[Full CPU upgrade documentation →](docs/cpu-upgrade/README.md)**

### EISA Expansion

The Compaq Portable 486c has two EISA card slots — not a lot of real estate, so every slot counts!

#### Sound Blaster AWE32 IDE/MKP CSP (CT3900)

The Compaq has no onboard audio, so one EISA slot is dedicated to a **Creative Sound Blaster AWE32 (CT3900)**. This gives full Sound Blaster and AdLib compatibility for DOS games, OPL3 FM synthesis, and the EMU8000 wavetable synthesizer with 512 KB onboard sample RAM. The CT3900 was chosen specifically because it is not Plug and Play — in 1994, "Plug and Play" mostly meant "Plug and Pray." The CT3900 uses jumpers, works at boot, no drama!

**[Full Sound Blaster documentation →](docs/soundblaster/README.md)**

#### SCM ISAC2PR10 ISA PCMCIA Adapter

PCMCIA was designed for laptops — but nobody said a 25-pound luggable couldn't crash the party! The second EISA slot holds an ISA PCMCIA adapter card (SCM Microsystems ISAC2PR10, Vadem VG-469 chipset) providing dual PC Card slots. Why waste an EISA slot on one device when you can turn it into two hot-swappable expansion slots?

The dual slots open up the wide range of 1990s PC Cards — network adapters, flash storage, modems, and SCSI controllers.

Currently installed:

- **Cisco Aironet 350 (AIR-PCM350)** — 802.11b wireless LAN adapter for WiFi connectivity
- **SanDisk CF adapter** — CompactFlash-to-PCMCIA adapter for flash storage, supports hot-swapping in DOS and Windows 3.1 and doubles as an easy file transfer method

Previously I used a Xircom RealPort Ethernet 10/100 (RE-100), but it hogged both slots. Greedy.

**[Full PCMCIA adapter documentation →](docs/pcmcia-adapter/README.md)**

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
│   ├── psu-rebuild/
│   │   ├── README.md                    # PSU rebuild documentation
│   │   └── images/                      # PSU recap and testing photos
│   ├── keyboard-restoration/
│   │   └── README.md                    # Keycap retrobrighting and cable notes
│   ├── cpu-upgrade/
│   │   └── README.md                    # AMD Am5x86 133 MHz upgrade guide
│   ├── pcmcia-adapter/
│   │   └── README.md                    # SCM ISAC2PR10 ISA PCMCIA adapter notes
│   ├── soundblaster/
│   │   └── README.md                    # Sound Blaster AWE32 CT3900 notes
│   └── images/                          # General project photos
└── .gitignore
```

## Contributing

If you're working on a similar Compaq Portable restoration, feel free to open an issue or pull request with your findings. Community knowledge around these machines is scarce, and every bit helps.

## References

- [VCFed Forum Thread](https://forum.vcfed.org/index.php?threads/compaq-portable-486c-restore-and-upgrade.73098/) — My restoration thread with discussion and community Q&A
- [DOSReloaded Forum Thread (German)](https://dosreloaded.de/forum/thread/7354-compaq-portable-486c-66/?postID=254850#post254850) — Detailed write-up by *Beckenrandschwimmer* covering the display replacement with oscilloscope measurements and circuit design
- [Compaq Portable 486 Pictures & Firmware (Bitsavers)](http://bitsavers.org/pdf/compaq/Compaq_Portable_486/pictures/) — Reference photos and firmware dumps

## License

This project is licensed under the DBAD License — see [LICENSE](LICENSE) for details.
