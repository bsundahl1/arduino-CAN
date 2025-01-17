# Arduino CAN

An Arduino library for sending and receiving data using CAN bus.

## Compatible Hardware

* [Microchip MCP2515](http://www.microchip.com/wwwproducts/en/en010406) based boards/shields
  * [Arduino MKR CAN shield](https://store.arduino.cc/arduino-mkr-can-shield)
* Microchip MCP25625 based boards/shields
* [Espressif ESP32](http://espressif.com/en/products/hardware/esp32/overview)'s built-in [SJA1000](https://www.nxp.com/products/analog/interfaces/in-vehicle-network/can-transceiver-and-controllers/stand-alone-can-controller:SJA1000T) compatible CAN controller with an external 3.3V CAN transceiver

### Microchip MCP2515/MCP25625 wiring

| Microchip MCP2515 | Arduino |
| :---------------: | :-----: |
| VCC | 5V |
| GND | GND |
| SCK | SCK |
| SO | MISO |
| SI | MOSI |
| CS | 10 |
| INT | 2 |


`CS` and `INT` pins can be changed by using `CAN.setPins(cs, irq)`. `INT` pin is optional, it is only needed for receive callback mode. If `INT` pin is used, it **must** be interrupt capable via [`attachInterrupt(...)`](https://www.arduino.cc/en/Reference/AttachInterrupt).

**NOTE**: Logic level converters must be used for boards MCP2515
which operate at 3.3V. The MCP25625 can run on 3.3V or 5V power,
resolving this issue.

### Espressif ESP32 wiring

Requires an external 3.3V CAN transceiver, such as a [TI SN65HVD230](http://www.ti.com/product/SN65HVD230).

| CAN transceiver | ESP32 |
| :-------------: | :---: |
| 3V3 | 3V3 |
| GND | GND |
| CTX | 5 |
| CRX | 4 |

`CTX` and `CRX` pins can be changed by using `CAN.setPins(rx, tx)`.

## Installation

As this is a fork of https://github.com/sandeepmistry/arduino-CAN with
additional patches, you have to use git to install this version of the library:

```sh
cd ~/Documents/Arduino/libraries/  # ~/Arduino/libraries on Mac OS
git clone https://github.com/timurrrr/arduino-CAN CAN
```

## API

See [API.md](API.md).

## Examples

See [examples](examples) folder.

## License

This library is [licensed](LICENSE) under the [MIT Licence](http://en.wikipedia.org/wiki/MIT_License).
