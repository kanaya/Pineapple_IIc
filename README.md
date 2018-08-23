# Pineapple IIc

## Overview

Pineapple IIc is a _card_ version of MIDI-computer _Pineapple II._ It can convert 7 analog voltage levels (0-5V) to MIDI Note On/Off signals.

## How to build

### Basics

* Install all components except for RN2.
* Install RN2 if _pull-down_ resistors are required.
* _Short_ 3 leftmost JP1 pins vertically. (Leave the rightmost pins open.)

### Relay mode

* _Short_ the rightmost JP1 pins vertically.

### I2C mode

* _Open_ 3 leftmost JP1 pins.

### Alternative connectors

If you want to use panel-mounted MIDI connectors and/or DC jack, use MIDI-IN-ALT, MIDI-OUT-ALT, PWR instead of MIDI-IN, MIDI-OUT, DC12V respectively.

## How to connect

### Pineapple II compatible mode

Supply DC12V to DC Jack connector.


## Arduino Pinout

| Arduino Micro | Signal     | JP1                               |
|---------------|------------|-----------------------------------|
| RX            | MIDI IN    |                                   |
| TX            | MIDI OUT   |                                   |
| D2/SDA        | SW0/SDA    | 1-5, open to use I2C              |
| D3PWM/SCL     | PWM0/SCL   | 2-6, open to use I2C              |
| D4/A6         | A6         |                                   |
| D5PWM         | PWM1       |                                   |
| D6PWM/A7      | PWM2       |                                   |
| D7            | SW1        | 3-7, open to use D7 independently |
| D8/A8         | SW2        |                                   |
| D9PWM/A9      | PWM3       |                                   |
| D10PWM/A10    | PWM4       |                                   |
| D11PWM        | PWM5       |                                   |
| D12/A11       | SW3        |                                   |
| D13PWM        | PWM6/Relay | 4-8, close to use relay           |

