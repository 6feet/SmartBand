# Smart Band!?

Misusing a $5 Fitness Tracker as wearable development platform.

![](https://des.gbtcdn.com/uploads/pdm-desc-pic/Electronic/image/2017/11/24/20171124181750_76413.jpg)


## Hardware

### What?

For this cost, this smart band has a looot of features:

  - nRF52 MCU + BLE by Nordic Semiconductor (compatible Arduino)
  - KX023 3d Accelerometer by Kionix
  - SSD1306 screen
  - Heart rate monitor
  - Vibrator
  - Capacitive touch button
  - Battery and charging circuit
  - Available GPIOs (UART, etc)


### Where?

To get it, you can try these links:

  - $10 on [Ebay](https://www.ebay.com/itm/NRF52832-MPOW-DS-D6-SmartWatch-FitnessTracker-WristBand-Bracelet/274016615669)
  - $10 on [Amazon](https://www.amazon.com/gp/offer-listing/B07Z2PW73N)
  - $5 on [Aliexpress](https://www.aliexpress.com/item/4000044393035.html) (not tested but [normally equivalent](https://github.com/fanoush/ds-d6/#ds-d6))

And if none of them works, this page should help:

https://github.com/fanoush/ds-d6


### More?

The following links should help understand the pinout:

  - https://github.com/fanoush/ds-d6/wiki/Hardware#register-dumps
  - https://github.com/atc1441/D6-arduino-nRF5/blob/master/variants/DSD6/variant.h
  - https://github.com/atc1441/D6Emulator/blob/master/D6Emulator/D6Emulator.ino#L369-L381


## Software

### How?

To upload custom firmware on this smartband, you can simply use this app:

https://play.google.com/store/apps/details?id=com.atcnetz.ble.readwrite


To customize the firmware, just clone this repo, and compile the code with the following adapted Arduino library environment:

https://github.com/atc1441/D6-arduino-nRF5


### Who?

This would not be possible without the excellent work by "ATC1441":

  - https://github.com/atc1441
  - https://twitter.com/atc1441

He made this great video to understand what is going on if you are new here :)

[![YoutubeVideo](https://img.youtube.com/vi/3gjmEdEDJ5A/0.jpg)](https://www.youtube.com/watch?v=3gjmEdEDJ5A)

