# Pineapple IIc

_Edition 2.0.1 for Pineapple IIc version 2.0.1-Alpha._

Pineapple IIc is an artist-friendly computer that can convert analog voltage to MIDI signal.

## Overview

Pineapple IIc can take up to 4 analog inputs (0-5V or 0-50mA) and converts them to MIDI signals. An edge of the analog signal (e.g. 0V to 0.1V or 0 to 1mA) causes MIDI Note On signal. Continuous change of the input voltage causes MIDI Control Change, and drop to 0V (or 0mA) causes MIDI Note Off.

Up to 4 analog sensors can be attached to Pineapple IIc. The sensor can be **(1) voltage mode:** analog voltage output (0V when not active), **(2) current mode:** variable resistance (nonconductive when not active).

Table. Sensor Port (16p ML connector)

| Pin | Meaning      |
|-----|--------------|
| S1  | Vcc          |
| S2  | GND          |
| S3  | GPIO 1       |
| S4  | Analog 1     |
| S5  | Vcc          |
| S6  | GND          |
| S7  | GPIO 2       |
| S8  | Analog 2     |
| S9  | Vcc          |
| S10 | GND          |
| S11 | GPIO 3       |
| S12 | Analog 3     |
| S13 | Vcc          |
| S14 | GND          |
| S15 | GPIO 4       |
| S16 | Analog 4     |



The GPIO 1, 2 and 3 can perform PWM output.

If the pin 3 of MIDI In+ is connected to GND at boot time, Pineapple II switches to _alternative_ mode.

Table. Working mode of Pineapple II

| Aux (m3) | Mode                                      |
|----------|-------------------------------------------|
| Open     | Default mode. Sensor to MIDI Out.         |
| GND      | Alternative mode. MIDI In to digital out. |



| Pin of Arduino Micro | Meaning            |
|----------------------|--------------------|
| D0                   | MIDI IN            |
| D1                   | MIDI OUT           |
| D2                   | SDA                |
| D3                   | SCL                |
| D4/A6                | Relay              |
| D5                   | Display 1, SW1     |
| D6/A7 (PWM)          | GPIO 1             |
| D7                   | Display 2, SW2     |
| D8/A8                | Display 3, SW4     |
| D9/A9 (PWM)          | GPIO 2             |
| D10/A10 (PWM)        | GPIO 3             |
| D11                  | Selector           |
| D12/A11              | GPIO 4             |
| D13                  | Indicator          |
| MOSI                 | Display 4          |
| MISO                 | ---                |
| SCLK                 | Display 5          |
| A0                   | Analog 1           |
| A1                   | Analog 2           |
| A2                   | Analog 3           |
| A3                   | Analog 4           |
| A4                   | SW8                |
| A5                   | Thermal sensor, ID |


# Components

| Kind             | Symbol | Specification   |
|------------------|--------|-----------------|
| Capacitor        | C1     | 474             |
|                  | C2     | 105             |
|                  | C3     | 104             |
|                  | C4     | 22u             |
|                  | C5     | 103             |
|                  | C6     | 103             |
|                  | C7     | 104             |
| Diode            | D1     | 1S3             |
|                  | D2     | 1S3             |
|                  | D3     | 1S3             |
| IC               | IC1    | 74LS07N         |
| Connector        | J1     | DC Jack         |
|                  | J2     | DIN 5p          |
|                  | J3     | DIN 5p          |
|                  | J4     | JST PH 2p       |
|                  | J5     | JST PH 3p       |
|                  | J6     | JST PH 5p       |
|                  | J7     | Pinheader 1x5   |
|                  | J11    | JST SH 4p       |
| Jumper           | JP1    | Pinheader 2x3   |
|                  | JP2    | Pinheader 1x3   |
| Relay            | K1     | G5V-1           |
| LED              | L1     | Any             |
| Optocoupler      | OK1    | TLP552          |
| FET              | Q11    | BSS138          |
|                  | Q12    | BSS138          |
| Resistor         | R1     | 473             |
|                  | R2     | 102             |
|                  | R3     | 221             |
|                  | R4     | 221             |
|                  | R5     | 221             |
|                  | R6     | 221             |
|                  | R11    | 102 (2012)      |
|                  | R12    | 102 (2012)      |
|                  | R13    | 102 (2012)      |
|                  | R14    | 102 (2012)      |
| Resistor Net     | RN1    | 10k 4-elements  |
|                  | RN2    | 4.7k 4-elements |
| Connector ML     | SV1    | 16p             |
| Transistor       | T1     | 2SC1815Y        |
| Micro Controller | MC1    | Arduino Micro   |
| Thermal Sensor   | U1     | DS18B20         |
| V. Regulator     | V1     | L7805           |
