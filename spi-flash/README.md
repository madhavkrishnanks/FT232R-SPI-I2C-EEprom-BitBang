# FT232R-SPI-Flash

## Objective

A datasheet-driven implementation of the Winbond W25Q64JV serial flash memory using Python and an FT232R USB-to-UART adapter.

This project focuses on understanding and implementing each SPI command directly from the datasheet rather than relying on existing libraries. Every implemented instruction is verified using a logic analyzer and interpreted against the datasheet.

This folder contains the original SPI flash notes and documentation consolidated into this repository.

## Wiring

| FT232R | W25Q64 |
|--------|---------|
| DTR | CLK |
| TX | DI (MOSI) |
| RX | DO (MISO) |
| RTS | CS |
| VCC | VCC (3.3V) |
| GND | GND |

## Hardware

- FT232R USB UART converter
- Winbond W25Q64JV
- Logic Analyzer
- Breadboard
- Jumper wires

## Notes

This project demonstrates how to perform direct low-level SPI communication by manipulating GPIO states and bus timing from Python. It is useful for debugging and understanding streaming bus transactions without higher-level drivers.

## Reference

Source repository:
https://github.com/madhavkrishnanks/FT232R-SPI-Flash
