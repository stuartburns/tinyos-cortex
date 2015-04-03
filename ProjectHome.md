This project ports [TinyOS](http://www.tinyos.net/) to small [ARM Cortex](http://en.wikipedia.org/wiki/ARM_architecture), such as Cortext-M3 and Cortex-M0, that are not supported officially.  This project is intended as a basis for electronics hobbyist.

[TinyOS main stream](https://code.google.com/p/tinyos-main/) already supports Cortex-M3 (SAM3S and SAM3U).

**`[NEW]`** New directory layout and smarter installation, though tinyos-cortex is empty.

PathStructure - brief explanation for installation **`[NEW]`**

ReleaseNews - _2012-01-22_

Currently I am planning to support:

  * NXP
    * LPC812 (20pin, 30MHz, 16KB Flash, 4KB RAM, Cortex-M0+)
    * LPC1114 (48pin, 50MHz, 32KB Flash,  8KB RAM, Cortex-M0)
    * LPC1227 (48pin, 30MHz, 128KB Flash, 8KB RAM, Cortex-M0)
    * LPC1313 (48pin, 72MHz, 32KB Flash,  8KB RAM, Cortex-M3)
    * LPC1343 (48pin, 72MHz, 32KB Flash,  8KB RAM, Cortex-M3, USB)

  * ~~Atmel~~
    * ~~SAM3S4A (48pin, 64MHz, 256KB Flash, 48KB RAM, Cortex-M3, USB)~~
    * ~~SAM3S3B (64pin, 64MHz, 256KB Flash, 48KB RAM, Cortex-M3, USB)~~


---


see also [tinyos-msp430](https://code.google.com/p/tinyos-msp430/)