# Project-local KiCad libraries

These libraries make the Nape KiCad project self-contained. The project library
tables in the parent directory resolve the existing symbol and footprint library
nicknames to these paths through `${KIPRJMOD}`.

## Contents

- `Nape_Symbols.kicad_sym`: all eleven symbols used by the schematic, copied
  from the definitions embedded in `Nape.kicad_sch`. PMW3610 and XIAO nRF52840
  originate from roBa.
- `_kicad_footprints.pretty/`: six footprints used by Nape and derived from roBa.
- `kbd_Parts.pretty/ResetSW.kicad_mod`: Reset switch footprint from
  [Salicylic-acid3/KiCAD_FootPrint](https://github.com/Salicylic-acid3/KiCAD_FootPrint).
- `kbd_SW_PCBA.pretty/Choc_v2_Hotswap_1u.kicad_mod`: Choc hot-swap footprint
  from [Salicylic-acid3/KiCAD_FootPrint](https://github.com/Salicylic-acid3/KiCAD_FootPrint).

The roBa-derived files are distributed under `GPL-3.0-only` as part of the Nape
PCB design. The two Salicylic-acid3 keyboard footprints are distributed under
the MIT License; see `LICENSE-Salicylic-acid3-KiCAD_FootPrint.txt`.
