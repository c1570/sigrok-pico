# sigrok-rp2350
https://github.com/c1570/sigrok-rp2350

Use an [RP2350(B) microcontroller](https://en.wikipedia.org/wiki/RP2350) as a logic analyzer and oscilloscope with [sigrok](https://sigrok.org/).

* work in progress
* twice the buffer size of sigrok-pico rp2040
* 32 digital channels on the RP2350B.
  * Use this with "Pimoroni PGA2350" or "WeAct RP2350B core board" or similar.
  * 48 channels are possible but need major firmware changes.
* 21 digital channels on the RP2350A (Pico 2 etc., untested).

You need an up to date sigrok to use this:
sigrok-cli 0.7.2 lacks the `raspberrypi-pico` driver.

# Old documentation

...of the rp2040 sigrok firmware at [pico-coder/sigrok-pico](https://github.com/pico-coder/sigrok-pico)...

As of 28 Sept 2023 this pull request has been merged into mainline sigrok (https://github.com/sigrokproject/libsigrok/pull/181)
It is highly recommended to install from https://sigrok.org/wiki/Downloads

Please start with the Getting Started page : https://github.com/pico-coder/sigrok-pico/blob/main/GettingStarted.md
/////////////////////////////////////////////////////////////////
Building this repo:
Bbuilding is not recommended, but some people insist on trying.....)

I once did a cross compile of PulseView for windows.  The instructions and installer are left in place for historical reference, they are likely out of date.
Instructions to download my build are here https://github.com/pico-coder/sigrok-pico/blob/main/pulseview/Readme.md
Again, please use the main sigrok installer.

For linux, many people have managed to combine my pull request into a libsigrok build. If you are on linux it's probably a practical experiment to try.  4GB of RAM is recommended for pulseview builds to avoid disk swap issues.  See SigrokBuildNotes.md

#
# sigrok-pico
Use a raspberry pi pico (rp2040) as a logic analyzer and oscilloscope with sigrok.
This implementation uses the pico SDK CDC serial library to communicate with sigrok-cli/pulseview through a sigrok driver.

## Directories:

pico_pgen is a simple digital function generator useful for creating patterns to test.

pico_sdk_sigrok is the pico sdk C code for the PICO RP2040 device.

The latest libsigrok code exists as a fork at https://github.com/pico-coder/libsigrok

## Files
PICOBuildNotes.md - build notes for building the PICO device assuming you have gone through the PICO C SDK "getting started with PICO".

SigrokBuildNotes.md - rough libsigrok build notes which will be depracated once raspberrypi_pico is mainline

GettingStarted.md - quick run down on setting things up.

AnalyzerDetails.md - details on supported modes of the analyzer and various limitations.

SerialProtocol.md - details of the "over the wire" protocol used between the sigrok driver and the device.
