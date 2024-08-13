Mouse Jiggler for Raspberry Pi Pico
===================================

This program turns the Raspberry Pi Pico into a simulated mouse that periodically moves a small amount. This can be used to prevent screensavers from triggering.

Installation
------------

1. Download `jiggler.uf2` from the [latest release](https://github.com/akhilharihar/pico-jiggler/releases/latest).
2. Plug in the Raspberry Pi Pico while holding the "BOOTSEL" button.
3. Drag the `jiggler.uf2` file into the "RPI-RP2" USB mass storage device that appears.

Building from source
--------------------

Clone this repo and run cmake commands to build project.

```
git clone https://github.com/akhilharihar/pico-jiggler && cd pico-jiggler
mkdir build && cd build
cmake ..
make
```

This will generate UF2 FILE with pico board appended to the file name eg: `pico-jiggler.uf2`
