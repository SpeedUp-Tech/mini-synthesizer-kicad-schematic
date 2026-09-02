# Engineering Limitations

This repository contains a generated Mini Synthesizer schematic-stage draft for engineering review. It does not establish that the design is electrically correct, safe, compliant, production-ready, or suitable for fabrication.

## Project-specific review items

- Verify the STM32F411CEU6 power pins, decoupling, reset, boot configuration, 8 MHz clock network, programming header, and firmware-dependent pin assignments.
- Verify TLV320DAC3101 and ATtiny402 pin mapping, supply sequencing, I2C/I2S behavior, configuration assumptions, clocking, output filtering, headphone loading, and speaker-interface requirements.
- Confirm the USB-C input implementation, protection, current budget, switched audio supply, 3.3 V and 1.8 V rails, regulator stability, sequencing, and thermal margin.
- Review the 4-by-4 key matrix, three potentiometer inputs, status LED driver, debounce behavior, and user-interface signal allocation.
- Verify every symbol pin map and footprint assignment against the selected component package before creating a PCB. This includes the MMBT3904 SOT-23 assignment recorded in the current schematic.
- Treat generic resistors, capacitors, and other base components as engineering-review values rather than procurement-ready selections; confirm tolerance, voltage rating, dielectric, power rating, temperature range, manufacturer, and lifecycle where the product requires them.

## Outputs not included

The release does not include PCB placement, routing, Gerbers, firmware, simulation, bench validation, EMC or safety testing, compliance evidence, mechanical integration, manufacturing documentation, or production engineering sign-off.
