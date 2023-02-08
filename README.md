# Silicon Labs firmware for Yellow and SkyConnect

This repository contains firmware for products made by Nabu Casa
which contain Silicon Labs hardware.

To flash the firmware to the device the [silabs-flasher](https://github.com/agners/silabs-flasher/)
can be used. Do flash a new firmware, make sure nothing else is accessing
the device. The Home Assistant Core container can be (mis)used to flash
a new firmware:

```
docker exec -it homeassistant /bin/bash
pip install "silabs-flasher[gpio]"

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
  * 7.0.1.0 ([release notes](https://www.silabs.com/documents/public/release-notes/emberznet-release-notes-7.0.1.0.pdf))
  * 7.0.2.0 ([release notes](https://www.silabs.com/documents/public/release-notes/emberznet-release-notes-7.0.2.0.pdf))
  * 7.1.1.0 ([release notes](https://www.silabs.com/documents/public/release-notes/emberznet-release-notes-7.1.1.0.pdf))
  * 7.1.3.0 ([release notes](https://www.silabs.com/documents/public/release-notes/emberznet-release-notes-7.1.3.0.pdf))
  * 7.1.4.0 ([release notes](https://www.silabs.com/documents/public/release-notes/emberznet-release-notes-7.1.4.0.pdf))
  * 7.2.1.0 ([release notes](https://www.silabs.com/documents/public/release-notes/emberznet-release-notes-7.2.1.0.pdf))

There are firmwares for two different Silicon Labs EFR32MG21 modules available.
Depending on HW version, the following must be used:

 * MGM210PA32JIA2 (Yellow v1.1 and later, PA32)
 * MGM210PB32JIA2 (Amber v1.0 and earlier, PB32)

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

## OpenThread RCP

The OpenThreadRCP directory contains firmares which implement the OpenThread
Radio Co-Processor (RCP) protocol through Spinel. The firmwares are largely
compatible with the upstream OpenThread Core and the Border Router.

For more details see [AN1256: Using the Silicon Labs RCP with the
OpenThread Border
Router](https://www.silabs.com/documents/public/application-notes/an1256-using-sl-rcp-with-openthread-border-router.pdf).

  * SL-OPENTHREAD/2.0.2.0_GitHub-3b79cb0d0 ([release notes](https://www.silabs.com/documents/public/release-notes/open-thread-release-notes-2.0.2.0.pdf))/


## RCP Multi-PAN

The RCPMultiPAN directory contains firmwares to run Silicon Labs multiprotcol
stack (rcp-uart-802154). The Silicon Labs EFR32 chip acts as the RCP (Radio
Co-Processor) and offers support for multiple protocols (multiple 802.15.4
PANs).

For more details, see [Silicon Labs AN1333: Running Zigbee, OpenThread, and
Bluetooth Concurrently on a Linux Host with
a Multiprotocol RCP](https://www.silabs.com/documents/public/application-notes/an1333-concurrent-protocols-with-802-15-4-rcp.pdf).

  * 4.0.0 ([release notes](https://www.silabs.com/documents/public/release-notes/open-thread-release-notes-2.0.0.0.pdf))
  * 4.0.1 ([release notes](https://www.silabs.com/documents/public/release-notes/open-thread-release-notes-2.0.1.0.pdf))
  * 4.0.2 ([release notes](https://www.silabs.com/documents/public/release-notes/open-thread-release-notes-2.0.2.0.pdf))
  * 4.1.0 ([release notes](https://www.silabs.com/documents/public/release-notes/open-thread-release-notes-2.1.0.0.pdf))
  * 4.1.1 ([release notes](https://www.silabs.com/documents/public/release-notes/open-thread-release-notes-2.1.1.0.pdf)/
  * 4.1.3 ([release notes](https://www.silabs.com/documents/public/release-notes/open-thread-release-notes-2.1.3.0.pdf))
  * 4.1.4 ([release notes](https://www.silabs.com/documents/public/release-notes/open-thread-release-notes-2.1.4.0.pdf))
  * 4.2.0 ([release notes](https://www.silabs.com/documents/public/release-notes/open-thread-release-notes-2.2.0.0.pdf))

Note: The release notes are specific to OpenThread (and versioned according to
its release version). However, it covers the Multi-PAN firmware, which uses
the Gecko SDK version number.

