# MCP7940 library header and source code<br>

This directory contains the two files that define the MCP7940 *Arduino* library.

The "MCP7940.h" is the library header file, and the program code is contained in the "MCP7940.cpp" file.

[![Zanshin Logo](https://zanduino.github.io/images/zanshinkanjitiny.gif) <img src="https://zanduino.github.io/images/zanshintext.gif" width="75"/>](https://zanduino.github.io)

## Usage

For this modified version, the following hardware abstraction layer (HAL) requirements must be satisfied:

* A header file `hal.h` providing access to HAL classes and methods.
* An `I2C` class within the `HAL` namespace with the following methods:
  - Write n bytes to the device: `write(uint8_t device_address, uint8_t * data_buffer, uint32_t length_in_bytes)`.
  - Write a byte to the device followed by n bytes (a register and data to place there): `write(uint8_t device_address, uint8_t register, uint8_t * data_buffer, uint32_t length_in_bytes)`.
  - Write one byte to the device, execute a repeated start, then read n bytes from the device: `writeRead(uint8_t device_address, uint8_t register, uint8_t * data_buffer, uint32_t length_in_bytes)`
* A `delay_ms(uint32_t milliseconds)` function within the `HAL` namespace.

Some further requirements may also be found. Typically, these will mirror the Arduino framework and should be added to `hal.h`.
