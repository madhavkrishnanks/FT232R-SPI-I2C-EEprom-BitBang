# Project overview

This repository consolidates two hardware experiments built around the FT232R USB-to-UART interface:

- a low-level SPI flash implementation using W25Q64
- a low-level I2C EEPROM implementation using AT24C256

Both projects use direct GPIO manipulation from Python to generate bus timing and verify the resulting protocol waveforms using a logic analyzer.

## Goals

- Understand hardware-level bus signaling without relying on vendor drivers.
- Verify protocol behavior with analyzer captures.
- Preserve original project documentation and make it easier to browse.
- Build a cleaner repository structure suitable for learning and future extension.
