# Pineapple IIc

## Congratulations!

You’ve got the latest version of Pineapple Computer named _Pineapple IIc._ But what is Pineapple Computer? Well, it is a MIDI computer that can covert analog signals to MIDI (digital) signal. Now you may want to ask, I guess, what is it for? The Pineapple Computer is an artist-friendly super-easy-to-use computer! You plug power, sensor, MIDI instrument, and boom! Everything is set up.

## How to set up (Hardware)

### Basics

Install the following components.

| Name        | Component         | Note                              |
|-------------|-------------------|-----------------------------------|
| MC1         | Arduino Micro 5V  | Using pin sockets is recommended. |
| IC1         | 74LS07            |                                   |
| OK1         | TLP552            |                                   |
| D1          | 1N4148            |                                   |
| R1-3        | 220               |                                   |
| R4          | 10k               |                                   |
| RN1         | 330               |                                   |
| RN2         | 10k               | Using pin sockets is recommended. |
| C1          | 0.1u              |                                   |
| C2-3        | 0.01u             |                                   |
| L1-7        | Vf=2.2 If=20m     |                                   |
| L8 (RCV)    | Vf=2.2 If=20m     |                                   |
| SW1         | HEX Complementary |                                   |
| JP1         | Pinheader 2x4p    | **Bridge 1-2, 3-4, 5-6.**         |
| Con. Analog | ML 14p            |                                   |
| Con. DC     | DC Jack           |                                   |
| Con. MIDI   | DIN 5p            |                                   |

### Non-basic usage

You can drive a relay, I2C devices, and TLC5940 PWM driver by installing some other components on Pineapple IIc. Also you can replace some connectors so that you can use panel mounted connectors and install Pineapple IIc board in a case. For more detail, please read _Extending Pineapple IIc_.

## How to set up (Software)

Install _Pineapple IIc Basic_ sketch to run Pineapple IIc in _Basic_ mode.

## How to play

Connect the following plugs.

* DC---Supply DC 12V to DC Jack connector.
* MIDI---Connect Pineapple IIc's MIDI OUT and your instrument's MIDI IN.
* Sensors---To be written.

## Extending Pineapple IIc

### To use relay

Install the following components as well as _Basic_ components.

| Item        | Name | Spec.      | # |  Note |
|-------------|------|------------|---|-------|
| Transistor  | T1   | 2SC1815    | 1 |       |
| Diode       | D2   | 1N4148     | 1 |       |
| Resistor    | R5-6 | 10k        | 2 |       |
| Relay       | K1   | G5V-1 DC5V | 1 |       |
| Con.        | Relay | PH 3p     | 1 |       |

Also you need to **bridge 7-8 of JP1.**

### To use I2C

Install the following components as well as _Basic_ components.

| Item                   | Name | Spec.      | # |  Note                       |
|------------------------|------|------------|---|-----------------------------|
| Signal level converter | IC2  | PCA9517ADP | 1 | Put A-side up, B-side down. |
| Resistor               | R7-8 | 6.8k       | 2 |                             |
| Con.                   | I2C  | SH 5p      | 1 | D7 operates at **5V.**      |

You need to **un-bridge 1-5, 2-6, 3-7 of JP1.** (D2/SDA and D7 are connected to SW1, and D3PWM/SCL is connected to PWM0 via JP1.)

### To use RST

Install the following components at back side as well as _Basic_ components.

| Item | Name       | Spec.   | # |  Note |
|------|------------|---------|---|-------|
| Con. | RST (Back) | PH 2p   | 1 |       |

### To use LIGHTDRIVE

Install the following components as well as _Basic_ components **except for SW1.** Since Arduino's D8 and D12 pins share SW1 connections and LIGHTDRIVE pins, you need to remove SW1.

| Item | Name       | Spec.        | # |  Note |
|------|------------|--------------|---|-------|
| Con. | LIGHTDRIVE | Pinheader 7p | 1 |       |

The LIGHTDRIVE pinouts are:

| Lightdrive | Meaning | Arduino Pin |
|------------|---------|-------------|
| 1          | Vcc     |             |
| 2          | GND     |             |
| 3          | GSCLCK  | D5PWM       |
| 4          | BLANK   | D8          |
| 5          | XLAT    | D12         |
| 6          | SCLCK   | SCLK        |
| 7          | SIN     | MOSI        |

### To use extra GND pins

Install the following components at back side as well as _Basic_ components.

| Item | Name       | Spec.                 | # |  Note |
|------|------------|-----------------------|---|-------|
| Con. | GND (back) | Pinheader/socket 2x3p | 1 |       |

### To use panel-mounted MIDI connector

Install the following components at back side as well as _Basic_ components.

| Item | Name        | Spec.        | # |  Note |
|------|-------------|--------------|---|-------|
| Con. | MIDI (back) | PH 5p        | 1 |       |

### To use panel-mounted DC Jack

Install one of the following components as well as _Basic_ components.

| Item | Name        | Spec.        | # |  Note |
|------|-------------|--------------|---|-------|
| Con. | PWR1        | Pinheader 2p | 1 |       |
| Con. | PWR2 (back) | PH 2p        | 1 |       |

### To use XOUT

XOUT is designed for extra MIDI OUT capability. It is a direct output of Open Collector so that you may want to install 220-ohm resistor for use as MIDI OUT.

Install the following components as well as _Basic_ components.

| Item | Name | Spec.        | # |  Note |
|------|------|--------------|---|-------|
| Con. | XOUT | Pinheader 5p | 1 |       |

### To use DIGITAL extension

You can hook L1-L7 driver pins by using DIGITAL pins. It also provides +3.3V DC.

Install the following components as well as _Basic_ components.

| Item | Name   | Spec.        | # |  Note |
|------|--------|--------------|---|-------|
| Con. | DIGITL | Pinheader 9p | 1 |       |

### To stack multiple cards

To stack multiple cards, you can do one of the following options.

* Use spacer. _Pineapple IIc_ has four M2 holes at each corners ((3, 3), (88, 3) (88, 52), (3, 52) mm).
* Use Pinheaders of Vcc (bottom left), 3V3 (bottom right), _Pogo_ (top right), Vcc (top left) and perhaps GND (next to the Vcc at top left).

## Technical notes

### Arduino Pinout

| Arduino Micro | Signal     | JP1                               |
|---------------|------------|-----------------------------------|
| RX            | MIDI IN    |                                   |
| TX            | MIDI OUT   |                                   |
| D2/SDA        | SW0/SDA    | 3-4, open to use I2C              |
| D3PWM/SCL     | PWM0/SCL   |                                   |
| D4/A6         | A6         |                                   |
| D5PWM         | PWM1       |                                   |
| D6PWM/A7      | PWM2       |                                   |
| D7            | SW1        | 5-6, open to use D7 independently |
| D8/A8         | SW2        |                                   |
| D9PWM/A9      | PWM3       |                                   |
| D10PWM/A10    | PWM4       |                                   |
| D11PWM        | PWM5       |                                   |
| D12/A11       | SW3        |                                   |
| D13PWM        | PWM6/Relay | 7-8, close to use relay           |
| A0-5          | A0-5       |                                   |

### JP1 Pinout

| JP1 | Signal                 | JP1 | Signal |
|-----|------------------------|-----|--------|
| 1   | Level Converter Enable | 2   | GND    |
| 3   | D2SDA (SW0/SDA)        | 4   | SW0    |
| 5   | D7 (SW1)               | 6   | SW1    |
| 7   | D13PWM (PWM6/Relay)    | 8   | Relay  |
