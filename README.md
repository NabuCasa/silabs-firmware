# Silicon Labs firmware for Yellow and SkyConnect

This repository contains firmware for products made by Nabu Casa
which contain Silicon Labs hardware.

To flash the firmware refer to the [Flash Silicon Labs radio firmware manually](https://github.com/NabuCasa/silabs-firmware/wiki/Flash-Silicon-Labs-radio-firmware-manually)
wiki page.

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
  * 7.2.0.0 ([release notes](https://www.silabs.com/documents/public/release-notes/emberznet-release-notes-7.2.0.0.pdf))
  * 7.2.1.0 ([release notes](https://www.silabs.com/documents/public/release-notes/emberznet-release-notes-7.2.1.0.pdf))
  * 7.2.2.0 ([release notes](https://www.silabs.com/documents/public/release-notes/emberznet-release-notes-7.2.2.0.pdf))

Firmware for Home Assistant Yellow (v1.1 and later, MGM210PA32JIA2 based) and
Home Assistant SkyConnect (EFR32MG21A020F512IM32 based) are available.

All firmware use  UART as communication interface with the following
configuration:
 * Baudrate: 115200
 * Flow Control: Hardware

For the exact EmberZNet configuration please refer to the [Zigbee EmberZNet NCP firmware configuration](https://github.com/NabuCasa/silabs-firmware/wiki/Zigbee-EmberZNet-NCP-firmware-configuration).

## OpenThread RCP

The OpenThreadRCP directory contains firmares which implement the OpenThread
Radio Co-Processor (RCP) protocol through Spinel. The firmwares are compatible
with upstream OpenThread Border Router.

For more details see [AN1256: Using the Silicon Labs RCP with the
OpenThread Border
Router](https://www.silabs.com/documents/public/application-notes/an1256-using-sl-rcp-with-openthread-border-router.pdf).

  * SL-OPENTHREAD/2.0.2.0_GitHub-3b79cb0d0 ([release notes](https://www.silabs.com/documents/public/release-notes/open-thread-release-notes-2.0.2.0.pdf))/
  * SL-OPENTHREAD/2.2.2.0_GitHub-91fa1f455 ([release notes](https://www.silabs.com/documents/public/release-notes/open-thread-release-notes-2.2.2.0.pdf))/


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
  * 4.2.1 ([release notes](https://www.silabs.com/documents/public/release-notes/open-thread-release-notes-2.2.1.0.pdf))
  * 4.2.2 ([release notes](https://www.silabs.com/documents/public/release-notes/open-thread-release-notes-2.2.2.0.pdf))

Note: The release notes are specific to OpenThread (and versioned according to
its release version). However, it covers the Multi-PAN firmware, which uses
the Gecko SDK version number.
