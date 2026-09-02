# Mini Synthesizer KiCad Schematic

> Schematic-stage draft for engineering review. This repository does not claim electrical validation, safety, compliance, manufacturability, or production readiness.

Editable four-sheet KiCad schematic for a compact STM32-based synthesizer with USB-C power, controls, and an audio codec path, generated with SpeedUp for engineering review.

SpeedUp is an AI schematic generator that turns product requirements into structured schematic sheets and an editable KiCad project for engineering review.

## Public project brief

> Create an editable mini synthesizer schematic organized into POWER, CONTROL, UI, and AUDIO sheets. Use USB-C power input with protected 3.3 V and 1.8 V rails; an STM32F411CEU6 controller with an 8 MHz crystal and programming header; a 16-key performance and function interface with three potentiometers; and a TLV320DAC3101 audio path with headphone and speaker connections plus an ATtiny402 support controller. Treat the output as a schematic-stage draft for engineering review.

The complete public requirement is preserved in [PRODUCT_REQUIREMENT.md](PRODUCT_REQUIREMENT.md).

## Architecture at a glance

![Mini Synthesizer hierarchical schematic structure](evidence/structure-diagram.png)

The KiCad project is divided into four editable hierarchical sheets:

| Sheet | Implemented design evidence |
| --- | --- |
| `POWER` | USB-C input, input protection, switched 5 V audio supply, 3.3 V regulation, and power-good supervision. |
| `CONTROL` | STM32F411CEU6 controller, 8 MHz crystal, programming header, key-matrix signals, parameter inputs, and I2S control signals. |
| `UI` | Thirteen note keys, three function keys, three potentiometers, and a status LED driver. |
| `AUDIO` | TLV320DAC3101 audio codec path, RT9013 1.8 V rail, ATtiny402 support controller, headphone output, and speaker connection. |

![Mini Synthesizer audio schematic sheet](evidence/schematic-overview.png)

## Quick technical answers

- **Primary controller:** STM32F411CEU6.
- **Audio device:** TLV320DAC3101IRHBR with an I2S connection to the controller.
- **User controls:** 16 keys and three PTV09A-series potentiometers.
- **Power input:** USB-C, with project sheets for 3.3 V and audio-related supply handling.
- **Editable format:** KiCad 10 project and hierarchical `.kicad_sch` files.
- **PCB output:** Not included.

## What SpeedUp produced

SpeedUp converted the product requirement into a structured, editable KiCad project package. The repository contains the evidence actually present in the audited bundle:

- `hardware/` — Editable KiCad hardware files (6 files).
- `bom/` — Bill of materials (1 file).
- `evidence/` — Block diagrams, schematic screenshots, and other project evidence (2 files).
- `LICENSES/` — Approved license texts and references (2 files).

The engineering-review BOM was freshly exported from the included schematic and contains 55 grouped rows covering 120 unique references. It is not a procurement BOM. If a downstream edit creates a discrepancy, the current `.kicad_sch` files are the project source of truth and the BOM should be regenerated.

This release does not claim to include PCB placement, routing, Gerbers, firmware, simulation, or bench validation.

Some standalone project-local library exports are intentionally absent from this public package; see [provenance/EXCLUDED_ASSETS.md](provenance/EXCLUDED_ASSETS.md).

## Open in KiCad

1. Install KiCad 10 or a compatible version.
2. Download and extract the latest release, or clone this repository.
3. Open the `.kicad_pro` file under `hardware/`.
4. Review embedded symbols, hierarchy, pin mappings, and footprint assignment strings. Standalone library exports listed in [provenance/EXCLUDED_ASSETS.md](provenance/EXCLUDED_ASSETS.md) were excluded from the public package.

## Download

[Download the public editable KiCad project package from the latest GitHub Release](https://github.com/SpeedUp-Tech/mini-synthesizer-kicad-schematic/releases/latest).

Release version: `v0.1.0`. This project was generated from product requirements using SpeedUp and is intended as a starting point for engineering review.

## Engineering status

Read [ENGINEERING_LIMITATIONS.md](ENGINEERING_LIMITATIONS.md) before using or modifying the files. Component choices, ratings, power behavior, interfaces, protection, thermal assumptions, RF/EMC, safety, compliance, test, manufacturing, and production release all require qualified engineering review.

## Licensing and provenance

See [LICENSE_SCOPE.md](LICENSE_SCOPE.md) and [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md). Copyright and license scope do not establish engineering fitness or transfer rights in third-party materials.

## Links

- [SpeedUp](https://speed-up.ai/)
- [Live project demo](https://speed-up.ai/demo/mini-synthesizer/)
- [Mini Synthesizer project case study](https://speed-up.ai/blog/mini-synthesizer-kicad-schematic/)

KiCad is a trademark of the KiCad project. SpeedUp is independent and is not affiliated with or endorsed by the KiCad project.
