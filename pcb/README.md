# PCB

Open `Nape.kicad_pro` with KiCad 10.

The project includes all symbols and custom footprints it references under
`libraries/`. The project-local `sym-lib-table` and `fp-lib-table` use
`${KIPRJMOD}`, so no global custom-library setup is required.

The PCB design files in this directory are licensed under `GPL-3.0-only`. See [`LICENSE`](LICENSE).

The PMW3610 circuit is derived from [kumamuk-git/roBa](https://github.com/kumamuk-git/roBa), licensed under GPL-3.0, and modified for Nape.

## Fabrication and assembly files

- `gerber/` contains the Gerber and plated/non-plated drill files exported in
  April 2025 for a previous PCB order. The board outline and drill coordinates
  match the current KiCad 10 design; KiCad 8 and 10 produce some differently ordered
  Gerber commands and aperture definitions.
- `pcba/Nape_bom.csv` and `pcba/Nape_cpl.csv` are the BOM and placement data
  from that order. They are JLCPCB ordering references, not a substitute for
  checking the current board and parts before a new order.

The `BT1` placement and rotation in the CPL were corrected manually for the
assembly order. **Do not replace this row with an unreviewed KiCad export.**
Check the assembly preview and component orientation before submitting any
new PCBA order.

The LCSC part numbers in the PMW3610 circuit are inherited from roBa and match
the JLCPCB-assembled configuration tested with Nape. Some LCSC part
specifications differ from the nominal values displayed in the schematic. In
particular, the BOM uses `C19666` for capacitors with several different
nominal values; verify the actual part specifications and availability before
reordering.
