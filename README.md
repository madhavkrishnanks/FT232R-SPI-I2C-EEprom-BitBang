# FT232R SPI + I2C Bit-Bang Experiments

This repository combines two FT232R hardware experiments into one organized, easy-to-navigate project:

- FT232R SPI Flash exploration using a Winbond W25Q64 flash device
- FT232R I2C EEPROM communication using an AT24C256 EEPROM

The goal is to document how these devices can be controlled directly from Python using the FT232R USB-to-UART adapter, without relying on vendor libraries, and to validate the bus activity with a logic analyzer.

## Repository layout

```text
.
├── README.md
├── LICENSE
├── spi-flash/
│   ├── README.md
│   └── Documentation of SPI Protocol.pdf
├── i2c-eeprom/
│   ├── README.md
│   ├── Python Code
│   ├── Images/
│   │   ├── DTR Test image.png
│   │   ├── Python break condition test.png
│   │   ├── Read Write test image.png
│   │   ├── Read_Write_test_image.png
│   │   ├── Single byte write test image.png
│   │   ├── Start condition test image.png
│   │   ├── TX line pulsing using 0x55 test image.png
│   │   └── ...
│   └── Documentation of i2c experiment.pdf
└── docs/
    └── project-overview.md
```

## Included upstream projects

This repository intentionally preserves the content of the original experiments in dedicated folders:

- `spi-flash/` → FT232R SPI Flash project
- `i2c-eeprom/` → FT232R I2C EEPROM project

Original repositories:

- https://github.com/madhavkrishnanks/FT232R-SPI-Flash
- https://github.com/madhavkrishnanks/FT232R-I2C-EEPROM

## Why this project matters

The FT232R is usually treated as a USB-UART chip, but it can also be used to control its GPIO lines directly for bit-banged protocols such as:

- SPI clock, MOSI, MISO, and chip select
- I2C SCL and SDA timing
- START/STOP condition generation
- Complete byte-level protocol verification with logic capture

This project demonstrates practical, low-level bus timing using Python and verifies every transaction with a logic analyzer.

## Hardware used

- FT232R USB-UART adapter
- Winbond W25Q64 flash memory
- AT24C256 EEPROM
- Logic analyzer (PulseView and similar)
- Breadboard and jumper wires
- Pull-up resistors for I2C
- USB cable and 3.3V / 5V power rails as needed

## Project overview

### 1) SPI flash experimentation

The SPI work focuses on implementing the Winbond flash protocol directly from the datasheet. Instead of using a ready-made library, the project steps through the SPI command set and validates each command with logic-analyzer captures.

Key concepts:

- SPI mode and timing
- Chip select handling
- Direct command verification from the datasheet
- Read/write debugging at the bus level

### 2) I2C EEPROM experimentation

The I2C work focuses on generating START/STOP conditions, transmitting bytes, and reading back EEPROM contents using a manual bit-bang implementation over FT232R pins.

Key concepts:

- DTR as SCL
- TX/RX break conditions as SDA control
- EEPROM write and read transactions
- Logic analyzer verification of actual waveform timing

## Folder reference

### `spi-flash/`

Contains the original SPI flash project documentation and reference material.

### `i2c-eeprom/`

Contains the original I2C EEPROM project documentation, waveform images, and Python experiments.

### `docs/project-overview.md`

A short internal overview of the combined repository and design intent.

## Suggested improvements

To make this repo more polished as a technical project, these are useful follow-ups:

- Add a consistent naming scheme for raw scripts and experiments
- Split the code into modules like `ft232r_gpio.py`, `spi_flash.py`, and `i2c_eeprom.py`
- Add a `requirements.txt`
- Add a `docs/` section with timing diagrams and screenshots
- Add a simple test harness for verifying serial port configuration
- Add cross-platform notes for Windows/Linux/macOS serial setup

## Notes

This repository is intended as a consolidated reference project for low-level FT232R bus experimentation. It is best suited to engineers and hobbyists who want to understand raw protocol generation and waveform verification.

## License

The repository includes the upstream license associated with the original project. See `LICENSE` for detailed terms.

## Contributions

This project is a documentation and learning repository. Contributions, cleanup, and improved examples are welcome.

---

For full project details, open the folders below:

- `spi-flash/README.md`
- `i2c-eeprom/README.md`
- `i2c-eeprom/Python Code`
