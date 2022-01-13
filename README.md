# Silicon Labs firmware for Yellow

This repository contains firmware for products made by Nabu Casa
which contain Silicon Labs hardware.

To flash the firmware to the device the [silabs-flasher](https://github.com/agners/silabs-flasher/)
can be used. Do flash a new firmware, make sure nothing else is accessing
the device. The Home Assistant Core container can be (mis)used to flash
a new firmware:

```
docker exec -it homeassistant /bin/bash
pip install silabs-flasher

curl -O https://github.com/NabuCasa/silabs-firmware/raw/main/EmberZNet/NabuCasa_EZSP_v6.9.2.0_PA32_ncp-uart-hw_115200.gbl
silabs-flasher --device=/dev/ttyAMA1 flash --cm4-gpio-reset --firmware NabuCasa_EZSP_v6.9.2.0_PA32_ncp-uart-hw_115200.gbl
```

## EmberZNet

The directory EmberZNet contains firmware which provide the EmberZNet
NCP (Network Co-Processor) firmware. EmberZNet is the Silicon Labs Zigbee
implementation.

  * 6.9.1.0 ([release notes](https://www.silabs.com/documents/public/release-notes/emberznet-release-notes-6.9.1.0.pdf))
  * 6.9.2.0 ([release notes](https://www.silabs.com/documents/public/release-notes/emberznet-release-notes-6.9.2.0.pdf))
  * 6.10.3.0 ([release notes](https://www.silabs.com/documents/public/release-notes/emberznet-release-notes-6.10.3.0.pdf))

There are firmwares for two different Silicon Labs EFR32MG21 modules available.
Depending on HW version, the following must be used:

 * MGM210PA32JIA2 (Yellow v1.1 and later)
 * MGM210PB32JIA2 (Amber v1.0 and earlier)

All firmware use  UART as communication interface with the following
configuration:
 * Baudrate: 115200
 * Flow Control: Hardware

By default the internal on-chip antenna is used. Firmware with use the external
antenna are marked with `_ext`.

Version 6.9.2.0 and newer have been compiled with the following EmberZNet configuration:

| Zigbee PRO stack macro           |   Value |
| -------------------------------- | ------: |
| EMBER_APS_UNICAST_MESSAGE_COUNT  |      32 |
| EMBER_PACKET_BUFFER_COUNT        |     128 |
| EMBER_NEIGHBOR_TABLE_SIZE        |      26 |
| EMBER_ADDRESS_TABLE_SIZE         |      32 |
| EMBER_SOURCE_ROUTE_TABLE_SIZE    |     200 |
