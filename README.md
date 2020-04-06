"Face touch" vibrating notifications with a sub $10 SmartBand:
[https://media.mit.edu/projects/saving-face](https://media.mit.edu/projects/saving-face)


![](extra/saving_face.gif)


## Hardware

### What?

A sub $10 fitness tracker as wearable development platform!?

For this cost, this smart band has a looot of features:

  - nRF52 MCU + BLE by Nordic Semiconductor (compatible Arduino)
  - KX023 3d Accelerometer by Kionix
  - SSD1306 screen
  - Heart rate monitor
  - Vibrator
  - Capacitive touch button
  - Battery and charging circuit
  - Available GPIOs (UART, I2C, etc)


### Where?

To get it, you can try these links:

  - $10 on [Ebay](https://www.ebay.com/itm/NRF52832-MPOW-DS-D6-SmartWatch-FitnessTracker-WristBand-Bracelet/274016615669) (DS-D6)
  - $10 on [Amazon](https://www.amazon.com/gp/offer-listing/B07Z2PW73N) (DS-D6)

If they're broken, [this list](https://github.com/fanoush/ds-d6) should help to find more.



## Software

### How?

To upload your [custom firmware](https://github.com/mitmedialab/SmartBand) on this smartband, you can simply use [this app](https://play.google.com/store/apps/details?id=com.atcnetz.ble.readwrite).

To customize the firmware, just clone this repo, and compile the code with [this adapted Arduino library environment](https://github.com/atc1441/D6-arduino-nRF5).


### More?

The following links should help understand the pinout:

  - [Register dumps](https://github.com/fanoush/ds-d6/wiki/Hardware#register-dumps)
  - [D6-arduino-nRF5 variant.h](https://github.com/atc1441/D6-arduino-nRF5/blob/master/variants/DSD6/variant.h)
  - [GPIO setup()](https://github.com/atc1441/D6Emulator/blob/master/D6Emulator/D6Emulator.ino#L369-L381)


### Who?

This would not be possible without the excellent work by [Sandeep Mistry](https://github.com/sandeepmistry/arduino-nRF5/), [fanoush](https://github.com/fanoush/ds-d6) and [atc1441](https://github.com/atc1441).

Bonus: ATC1441 made [this great video](https://www.youtube.com/watch?v=3gjmEdEDJ5A) to explain how the firmware upload works (among other things).

## Enjoy!

