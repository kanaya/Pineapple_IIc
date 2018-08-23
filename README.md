# Pineapple IIc

## Overview

Pineapple IIc is a _card_ version of MIDI-computer _Pineapple II._ It can convert 7 analog voltage levels (0-5V) to MIDI Note On/Off signals.

## How to build

### Basics

Install the following components.

* C1
* C2-3
* MC1
* Con DC

### Pineapple II compatible mode

* R3
* RN1
* RN2 (when _pull-down_ resistors are required)
* LED1-7
* IC1
* SW
* Con Analog
* Con MIDI OUT

### Pineapple Mini compatible mode

* R1-2
* R4-5
* K1
* D1-2
* T1
* OK1
* Con MIDI IN
* Con Relay


### Other optional components

* Con I2C
* Con PWM
* Con RST
* Con Vcc

To use I2C, be aware that Vcc and signal level are set to 5V. Pull-up resistors are not installed. Use level converter to communicate with 3.3V I2C devices.


