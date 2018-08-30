# Pineapple IIc

## Overview

Pineapple IIc is a _card_ version of MIDI-computer _Pineapple II._ It can convert 7 analog voltage levels (0-5V) to MIDI Note On/Off signals.

## How to build

### Basics

Install the following components.

| Component   | Value             | Note                              |
|-------------|-------------------|-----------------------------------|
| MC1         | Arduino Micro 5V  | Using pin sockets is recommended. |
| IC1         | 74LS07            |                                   |
| OK1         | TLP552            |                                   |
| D1          | 1N4148            |                                   |
| R1-3        | 220               |                                   |
| RN1         | 330               |                                   |
| RN2         | 10k               | To _pull-down_ sensor inputs.     |
| C1          | 0.1u              |                                   |
| C2-3        | 0.01u             |                                   |
| L1-7        | Vf=2.2 If=20m     |                                   |
| L8 (RCV)    | Vf=2.2 If=20m     |                                   |
| SW1         | HEX Complementary |                                   |
| JP1         | Pinhead 2x4p      | Short 1-4, 2-5, 3-7               |
| Con. Analog | ML 14p            |                                   |
| Con. DC     | DC Jack           |                                   |
| Con. MIDI   | DIN 5p            | Use PH 5p for panel mounted cons. |

### To use relay

| Component   | Value             | Note                              |
|-------------|-------------------|-----------------------------------|
| T1          | 2SC1815           |                                   |
| D2          | 1N4148            |                                   |
| R4-5        | 10k               |                                   |
| K1          | G5V-1             |                                   |
| Con. Relay  | PH 3p             |                                   |

### To use I2C

| Component   | Value             | Note                              |
|-------------|-------------------|-----------------------------------|
| IC2         | PCA9517ADP        | Use two 4p pinheads.              |
| RN6-7       | 6.8k              |                                   |
| Con. I2C    | SH 5p             | D7 operates at 5V.                |

### To use RST

| Component   | Value             | Note                              |
|-------------|-------------------|-----------------------------------|
| Con. RST    | PH 2p             |                                   |

### To use LIGHTDRIVE

| Component   | Value             | Note                              |
|-------------|-------------------|-----------------------------------|
| Con. LD     | Pinhead 7p        |                                   |

| Lightdrive | Meaning | Arduino Pin |
|------------|---------|-------------|
| 1          | GND     |             |
| 2          | Vcc     |             |
| 3          | GSCLCK  | D5          |
| 4          | BLANK   | D8          |
| 5          | XLAT    | D12         |
| 6          | SCLCK   | SCLK        |
| 7          | SIN     | MOSI        |

### To use DIGITAL extension

### To use XOUT

### To directly input 5V

### To directly input 12V



### To stack multiple cards

To stack multiple cards, you can do one of the following options.

* Use spacer. _Pineapple IIc_ has four M2 holes at each corners ((3, 3), (88, 3) (88, 52), (3, 52) mm).
* Use pinheads of GND (bottom left), Vin (bottom right), _Pogo_ (top right), and Vcc (top left).

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
