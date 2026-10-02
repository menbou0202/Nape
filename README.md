# Nape

Nape is a wireless trackball input device based on ZMK firmware.

![Nape](https://booth.pximg.net/d3ead6ac-a349-44f0-9838-a4a6494cbe44/i/6749348/7e38011e-0d1a-4fe5-9796-d21e054941be_base_resized.jpg)

## Files

- `case/`: STEP case files
- `doc/`: Documentation
- `pcb/`: KiCad 10 PCB design files, Gerber/drill files, and JLCPCB PCBA reference files

## Documentation

- [Build guide (Japanese)](doc/build-guide.md)

The firmware configuration is available at [menbou0202/zmk-config-nape](https://github.com/menbou0202/zmk-config-nape).

## License

- PCB design files in `pcb/` are licensed under `GPL-3.0-only`. See [`pcb/LICENSE`](pcb/LICENSE).
- Case design files in `case/` are licensed under `CERN-OHL-P-2.0`. See [`case/LICENSE`](case/LICENSE).

The PMW3610 circuit is derived from [kumamuk-git/roBa](https://github.com/kumamuk-git/roBa) and has been modified for Nape.

Before ordering a PCB or PCBA, read [`pcb/README.md`](pcb/README.md). In particular,
the placement of `BT1` in the supplied CPL was corrected manually for the
previous assembly order; do not replace it with an unreviewed KiCad export.
