# PCB

Open `Nape.kicad_pro` with KiCad 10.

The project includes all symbols and custom footprints it references under
`libraries/`. The project-local `sym-lib-table` and `fp-lib-table` use
`${KIPRJMOD}`, so no global custom-library setup is required.

The PCB design files in this directory are licensed under `GPL-3.0-only`. See [`LICENSE`](LICENSE).

The PMW3610 circuit is derived from [kumamuk-git/roBa](https://github.com/kumamuk-git/roBa), licensed under GPL-3.0, and modified for Nape.

Fabrication and ordering files are not included.

The LCSC part numbers in the PMW3610 circuit are inherited from roBa and match the JLCPCB-assembled configuration tested with Nape. Some LCSC part specifications differ from the nominal values displayed in the schematic.
