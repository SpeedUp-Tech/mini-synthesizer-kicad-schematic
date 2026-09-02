# Excluded Assets

The following files existed in the supplied private source bundle but are intentionally absent from this public package because their exact upstream provenance and redistribution permission were not established:

- `symbols/*.kicad_sym` — 15 standalone symbol-library files.
- `libs/ProjectFootprints.pretty/*.kicad_mod` — 26 standalone footprint files.
- `sym-lib-table` — project-local symbol-library mapping.
- `fp-lib-table` — project-local footprint-library mapping.
- `.history/`, `*.kicad_prl`, lock files, backups, and other local KiCad state.
- The superseded `BillOfMaterials.csv` and `BillOfMaterials.xlsx`; the public BOM was freshly exported from the current schematic.

The private source bundle was not modified. Exclusion applies only to the public repository and Release ZIP.
