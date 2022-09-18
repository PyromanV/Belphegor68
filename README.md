# Belphegor68

Original post at OLKB subreddit: https://www.reddit.com/r/olkb/comments/wz6s32

Project Belphegor, aka Belphegor68 is a completely 3D-printable DIY mechanical keyboard. The objective of this repository is to provide documentation, give access to production files, models and build instructions to anyone interested.

Originally, this was a project for me to learn KiCad while doing something useful, so this is not a professional design and I provide no warranty of any sort. Everything you do you are doing at your own responsibility.


## Features:

- Low-profile design using Kailh Choc keyswitches with hotswap
- Wired and Bluetooth LE support (running on nice!nano v2) - running custom Acedia firmware
- 68 keys in an ortholinear layout (60x 1u, 6x 1.25u, 2x 2u)
- 3D printable keycaps with or without legends (original design by **darryldh**, available at https://www.thingiverse.com/thing:4564253)
- 3D printable case
- Per-key RGB backlight and underglow
- Rotary encoder
- Joystick
- Low-power 2.2" 128x64 LCD
- 3200 mAh Li-pol cell

## Components

| Part | Where to get it | Price |
| ---- | --------------- | ----- |
| PCB | JLCPCB or your preferred PCB company | 74$ per 2 PCBs |
| Kailh Choc switches + sockets | Your preferred keyboard parts seller | 62$ |
| 12864-06D LCD | https://www.aliexpress.com/item/1005001621784395.html | 4$ |
| Joystick | https://www.aliexpress.com/item/4000263837725.html | 3$ |
| Rotary encoder (15mm shaft) | https://www.aliexpress.com/item/32759396738.html | 1$ |
| Nice!nano v2 | https://nicekeyboards.com/nice-nano/#find-a-store |  26$ |
| Samsung B800BC battery | https://www.aliexpress.com/item/1005002757023296.html | 8$ |
| Grand total |  | 141$ (my build was ~160-170$ due to taxes and shipping costs) |

I am not affiliated in any way with sellers mentioned above, these are just examples where I got my parts from.

## General recommendations
### LCD
For maximum power efficiency, desolder the SPI flash present on the underside of the PCB. The gray color variant is ideal, as it is most easily readable without backlight.
Jumper DISP_PSEL selects the power source the display uses. For maximum battery life (and/or short backlight timeouts), select AUX. If you did not remove the SPI flash (and/or don't care about power efficiency that much), select MAIN.

### Joystick
You can pick either the joystick module, or the raw joystick - the pad spacing is 2mm (not the traditional 2.54mm), but classic pin headers can be soldered directly on the pads. Connect solder jumpers on the PCB correspondingly to the variant you selected.

### nice!nano
I highly recommend using machine sockets, as they are much more low profile. Correspondingly, you can use diode (or resistor) legs on the nice!nano. If you are using a battery larger than 500 mAh (a minimum of 1000-1500 mAh is recommended for this project), be sure to solder the BOOST jumper on the nice!nano to shorten the charging time.

### Rotary encoder
If possible, get the 15mm shaft length variant. This is the ideal length for the stock case and is reasonably low-profile. Shorter encoders are possible, but are much harder to find.

### Keycaps
If possible, use blank keycaps directly from the Thingiverse link. They feel much nicer to the touch than those with the legends. I recommend printing them in PLA on a smooth PEI sheet treated with some sort of adhesive, oriented top-side down (see image below). No supports are needed, however you might want to use a 1mm brim, just to give the keys a bit more contact surface. Use lowest layer height preset available for maximum smoothness, 0.07mm seems ideal.

![obrazek](https://user-images.githubusercontent.com/16986988/188282542-0e87de21-b97e-4f2c-95eb-53202298870c.png)

## Credits

The Acedia firmware relies heavily on Adafruit's nRF52 Arduino core (https://github.com/adafruit/Adafruit_nRF52_Arduino), Neopixel library and Bluefruit libraries. It also uses u8g2 library (https://github.com/olikraus/u8g2) and PCA95X5 library (https://github.com/hideakitai/PCA95x5).

Used in the design is the footprint for nice!nano (https://github.com/bstiq/nice-nano-kicad) and the library for switch footprints (https://github.com/daprice/keyswitches.pretty). In some parts of the design, copyrighted fonts are used (http://www.peter-wiegel.de/Aurach_Tri.html, Our Sacred Rights by Bolt Cutter Design).
