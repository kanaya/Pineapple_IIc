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


