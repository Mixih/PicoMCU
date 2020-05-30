# PicoMCU

General purpose MCU breakout boards. Pico series boards are extra small or low
power and optimized for low profile embedding, and Micro series board are
general purpose development and prototyping boards with rich peripherals for testing.

## Contents

- PicoMEGA 328PB: Tiny (24x25mm) ATMEGA328PB breakout board

## File Layout

- `Lib`: shared component and footprint libraries
- `[Board Name]/`
  - `[Board Name].pro`: Main KiCAD project file
  - `[Board Name]_panelized.pro`: PCB layout panelized to fill 100x100mm fab
    area 

## Detailed Description and Specifications

Here are the details for each of the hardware projects hosted here.

### PicoMEGA 328PB

This is intended to be a general, low power ATMEGA328PB breakout board, sized as
to be small enough to be embedded in other products (i.e. hardware mods). By
keeping the MCU in sleep mode, power consumption can be greatly reduced,
making the 328PB a viable option for battery powered electronics.

**Feature:**
- Ultra-low quiescent (Iq = 400nA typ) current 3V3 switching regulator (300mA max) 
  w/ regulator bypass jumper for higher power.
- External crystal (designed for 8Mhz max system clock) with compensation caps
- AVCC supply filtering per Atmel AN042 (omit by jumpering over)
- Reset ESD protection and debounce/ext pullup
- ISCP header
- All hardware pins broken out (no more microwire to pad prototyping)
- Optional indication LED connected to pin E1 for status indication needs
  (leave unpopulated if using TWI1 or low power)

**Intentional Omissions:**
- PWR/UART Status LED: Waste of quiescent power. Kludge in if needed.
- Reset button: takes too much space. Use jumper wire instead if manual reset
  is needed
