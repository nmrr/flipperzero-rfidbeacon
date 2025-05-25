# flipperzero-rfidbeacon
A letter/number/symbol [Morse](https://fr.wikipedia.org/wiki/Code_Morse_international) beacon on **125 kHz** using **RFID** interface of the **Flipper Zero**

![banner](https://raw.githubusercontent.com/nmrr/flipperzero-rfidbeacon/main/img/banner-rfid.jpg)
(banner has been made with **Dall.E 2**)



Like Russia with their HF [letter beacons](https://en.wikipedia.org/wiki/Letter_beacon), it's possible to use the **Flipper Zero** as a letter/number/symbol [Morse](https://fr.wikipedia.org/wiki/Code_Morse_international) beacon. **Flipper Zero** has multiple RF interfaces (RFID, NFC and UHF) and it's possible to transmit raw data over these interfaces.

This application can transmit the whole alphabet (A to Z), numbers (0 to 9) and symbols in [Morse](https://fr.wikipedia.org/wiki/Code_Morse_international) on **RFID** interface (125 kHz). The range is about 5 meters with a small loop antenna. With an amplified loop, the range can extend to 15 meters according to my measurements.

## Gallery

Menu of the application:

<img src="https://github.com/nmrr/flipperzero-rfidbeacon/blob/main/img/screen1.png" width=25% height=25%> <img src="https://github.com/nmrr/flipperzero-rfidbeacon/blob/main/img/screen2.png" width=25% height=25%> <img src="https://github.com/nmrr/flipperzero-rfidbeacon/blob/main/img/screen3.png" width=25% height=25%>

Led of the **Flipper Zero** turns in red when transmitting. 

**Airspy Discovery HF+** **SDR** bas been used during these tests with a small loop antenna. Following measures have been made at a distance of 2m from the **Flipper Zero**.

**A** letter:

<img src="https://github.com/nmrr/flipperzero-rfidbeacon/blob/main/img/a.png" width=50% height=50%>

**3** number:

<img src="https://github.com/nmrr/flipperzero-rfidbeacon/blob/main/img/3.png" width=50% height=50%>

## Build the program

Assuming the toolchain is already installed, copy **flipper_rfidbeacon** directory to **applications_user**

Plug your **Flipper Zero** and build the RFID beacon:
```
./fbt launch_app APPSRC=applications_user/flipper_rfidbeacon
```

The program will automatically be launched after compilation

<img src="https://github.com/nmrr/flipperzero-rfidbeacon/blob/main/img/flipperzero.png" width=25% height=25%>

**Button assignments**: 

button  | function
------------- | -------------
**Left/Right** *[short press]* | Select the letter/number to transmit or the value of tick/pause in ms
**Left/Right** *[long press]* | Select the value of tick/pause in ms (more)
**Up/Down** *[short press]* | Navigate in the menu
**Ok** *[long press]*  | Enable/disable the transmission on 125 kHz
**Back** *[long press]*  | Exit

If you don't want to build this application, just simply copy **flipper_rfidbeacon.fap** on your **Flipper Zero** 

Build has been made with official toolchain (1.3.4), **API Mismatch** error may appear if you are using custom firmware. You can bypass this error but the program may crash.

## What's next ?
* ~~Choose the speed morse code~~ **DONE !**
* Transmit on NFC interface (13.56 MHz), range is wider than **RFID**
* Transmit on UHF interface (433 MHz, etc)
* Transmit personalized text message over the air

## Changelog

* 2025-05-25
  * Now it's possible to choose the transmission speed and the duration of the pause between transmissions

* 2023-07-11
  * Bug fixing
  * Symbols have been added
  * Morse code view has been added

* 2023-07-09
  * Initial release
