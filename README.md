# Quill STM32 WL

An Adafruit Feather-sized STM32 development board with integrated 868 MHz LoRa radio.

![3D render of Quill STM32 WL printed circuit board.](https://github.com/4f48/quill-stm32wl/blob/main/assets/3d_render.png)

## Features
- 32-bit ARM Cortex-M4 48 MHz microcontroller
- 256 kb flash, 64 kb RAM
- LoRa P2P/LoRaWAN - Up to 15 km range with a good antenna
- Programmable via SWD/UART/USB or control with AT Commands
- Built-in 3.3V linear regulator, providing up to 600 mA
- JST PH battery connector, built-in charging
- USB-C port for power supply, USB serial, battery charging
- Adafruit Feather-compatible dimensions
- STEMMA QT/Qwiic connector for soldering-free I2C

## Why though
I made Quill STM32 WL because I was unsatisfied with existing LoRa/long-range wireless development boards. They are either low-effort modules with ESP32 chips and huge power consumption, or use outdated parts and standards. I really liked the Adafruit Feather RP2040 RFM95 due to its size, feature-set, but it uses the older Semtech SX1276 LoRa IC.

As I was scrolling through ST Microelectronic's website (as one does), I found the perfect match: the STM32WLE5 family of microcontrollers. They offer an improved LoRa solution - with up to +22 dBm output power - in a sleek package, with an integrated, low-power STM32 microcontroller. I knew I had to try making something with it.

This was my second PCB project ever, and digging into more complicated concepts and trying to make a more dense board layout was a great challenge and an opportunity to improve my skills, before starting even more complicated projects.

## Usage
You can either use Quill STM32 WL as a standalone microcontroller, by programming it via the 3-pin SWD port or USB serial, or by sending AT Commands to the UART2 serial bus on pins 12 (RX) and 13 (TX) if you just wish to use the LoRa/LoRaWAN capabilities.

For programming instructions, see [RAK3172 Low Level Development Reference](https://docs.rakwireless.com/product-categories/wisduo/rak3172-module/low-level-development/). For using the AT Command interface, see [RAK3172 AT Command Manual](https://docs.rakwireless.com/product-categories/wisduo/rak3172-module/at-command-manual/).

This board is really versatile and could be used for a wide variety of projects. Note that the MCU is not as fast as some other offerings on the market, thus it can't be used for advanced data processing. However, Quill STM32 WL is more than capable of driving sensors (for example outdoor air monitoring) and some basic processing tasks, and thanks to its LoRa capabilities, it can radio data through long distances, ideally several kilometers with clear line-of-sight, which is particularly useful for off-grid IOT systems, as an example.

## Build one yourself!
In theory, you could make one of these boards for yourself. Uploading the provided Gerber files to a PCB manufacturing service (JLCPCB, PCBWay, Aisler, etc.) is simple, not very expensive and you usually get the boards quickly. You can find the production files in [/production](https://github.com/4f48/quill-stm32wl/tree/main/production).

However, placing and soldering the SMD components on the board may prove difficult, especially if you never soldered anything before. The design uses 0402 (1005 metric) passive components to fit into the space-confined size of the board. While it may not seem like on the screen, these components are REALLY tiny. You might find it easier to have the manufacturing service mount the components for you, but that gets very expensive very fast. For example, making 5 fully assembled Quill STM32 WL with JLCPCB would cost around $130 plus shipping. Reflow/hot-air soldering is an option, but you need to have specific equipment for that.

If you still want to make one of these yourself, feel free to explore these files in this repository, they will help greatly:

- Schematic: [schematic.svg](https://github.com/4f48/quill-stm32wl/blob/main/assets/schematic.svg)
- KiCad PCB: [quill-stm32wl.kicad_pcb](https://github.com/4f48/quill-stm32wl/blob/main/quill-stm32wl.kicad_pcb)
- Bill of Materials: [bom.csv](https://github.com/4f48/quill-stm32wl/blob/main/bom.csv)/[bom.ods](https://github.com/4f48/quill-stm32wl/blob/main/bom.ods)
- 3D model: [quill_stm32wl.step](https://github.com/4f48/quill-stm32wl/blob/main/assets/quill_stm32wl.step)