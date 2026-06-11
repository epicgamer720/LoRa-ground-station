# LoRa Ground Station

A compact, USB-connected LoRa receiver for pulling live telemetry off my rockets in flight. Built around an RP2040 + Semtech SX1262 on the 902–928 MHz ISM band, designed from scratch in KiCad. Pairs with my [rocket flight controller](https://github.com/epicgamer720/Flight-Controller-for-rockets).

<img width="709" height="880" alt="image" src="https://github.com/user-attachments/assets/10b6365f-b7e9-4174-8f22-df9424f3bdae" />
<img width="694" height="540" alt="image" src="https://github.com/user-attachments/assets/c02b8277-a09d-4c1a-9b49-6ab7081cbede" />
<img width="670" height="867" alt="image" src="https://github.com/user-attachments/assets/702c892f-ecd8-412a-8027-b42babcbd03c" />
<img width="1318" height="789" alt="image" src="https://github.com/user-attachments/assets/e41c9a8c-0482-4a13-9e7b-360099dcc10a" />

## Why I built it

The flight controller sends telemetry down over LoRa, but that's only half the link — you need something on the ground to actually receive it. Rather than buy an off the shelf LoRa dev board, I wanted to try my hand at RF design. It plugs into a laptop over USB-C and streams the rocket's altitude and position to a terminal or display in real time. It was also my way into RF design getting the 50 Ω antenna trace, the impedance matching, the RF switch, and the SX1262's TCXO reference right is a different challenge from a normal digital board, and I wanted to learn it on real hardware.

## Use cases

- **Live flight telemetry** — receive altitude, velocity, and GPS position from the rocket during flight, in real time.
- **Recovery tracking** — read out the last known GPS coordinates to find the rocket after landing.
- **Range testing** — bench-test link distance and signal quality before committing to a flight.
- **General LoRa receiver / dev tool** — works as a USB LoRa node for any other long-range telemetry or sensor project, not just rockets.

## Specifications

| Subsystem | Part / detail |
|---|---|
| MCU | RP2040 — dual-core Cortex-M0+ |
| Radio | SX1262 — sub-GHz LoRa transceiver |
| Band | 902–928 MHz ISM (915 MHz, US) |
| RF switch | PE4259 — TX/RX antenna switching |
| Reference | 32 MHz TCXO (ECS-TXO) for the radio |
| Antenna | SMA connector |
| Flash | W25Q128 — 16 MB QSPI for firmware |
| Clock | 12 MHz crystal for the RP2040 |
| Power | AP2112K-3.3 LDO, USB-C |
| Controls | 2× tactile buttons (BOOT / RESET) |


## 
## Built with

[KiCad](https://www.kicad.org/) · [Macondo](https://macondo.hackclub.com/)

