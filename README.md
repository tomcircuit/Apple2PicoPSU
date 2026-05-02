# Apple 2 Pico PSU
12V Input Power Supply retrofit for vintage Apple //e  computers

Many vintage Apple(R) ][ and // series computers suffer from power supply failure. These computers were fitted with switching power supplies (SMPS) that, for the time, were notable for their lightweight, quiet, and efficient characteristics. Time, however, has not been kind to these supplies, which are vulnerable to aging. There is no drop-in replacment unit, so most enthusiasts are forced to either repair their supply or replace with a modern retrofit. This project is of the latter type, and my motivation was when my Apple //e computer's power supply emitted the dreaded "magic smoke" (AFTER a complete re-cap, mind you) and resisted my efforts at repair.

First and foremost, this project is insprired by the "PicoRC" project family by DekuNukem, currently found here: https://github.com/dekuNukem/PicoRC
Note that this project is licensed under MIT License terms:

```
MIT License

Copyright (c) 2022 dekuNukem

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

I did not directly modify the Eagle PCB nor Schematic files, and this work is my own, but I do feel that it is only proper to give DekuNukem attribution for the inspiration for this project. I license my project under CC-BY-SA-4.0 which can accept an MIT License as an "inbound license", in the event that my work is determined to be derivative after all.

There, that out of the way...

It's a **Great Idea** to move the AC-DC converter to the **outside of the Apple's case** for many reasons some of which are: it's heavy, it generates heat, and it allows for the possiblity to scale the PSU Wattage as required by the peripheral load. Any 12VDC supply with sufficient wattage and mating connector can be used, so that only 12VDC goes into the computer via the rear panel.

The **PicoPSU** units that are aimed at Small Form Factor (SFF) PC's are an ideal solution to convert the incoming 12VDC to +5V, +15V and -12V. These are available from many sources, in varying Wattages. I chose an 80W type for my own use, which should be more than sufficient. All that is missing is the -5V which is (questionably) required by the Apple motherboard.

Like the PicoRC for the Apple, my Apple2PicoPSU provides a power switch, a 24-pin Molex connector for the PicoPSU, fuses for the +5V and +12V voltage rails, and a -5V regulator for the 'missing' rail. I adoped a similar "PCB-welded" construction of a back panel and circuit board, because it seemed like a very convenient way to satisfy the mechanical aspects.

Improvements over the original PicoRC for the Apple are the following:
* power switch suitable for switching the low-current PicoPSU enable 
* LED for each voltage rail, visible from the outside of the case
* copper tracks sized sufficiently for the anticipated current demand

It is this last point in particular that really drove me to re-engineer this concept; I am quite skeptical of the copper track widths used in the original. I have sized the copper tracks for at least 8A on the 5V rail, and 4A on the 12V rail, assuming 1oz Cu and a modest 15C temperature rise over ambient.

My project was executed in the very capable open-source and "completely free" KiCad 10.0 which is well supported by the usual Operating Systems suspects...

tomcircuit
01-MAY-2026