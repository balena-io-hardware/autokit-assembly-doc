# Autokit assembly and BoM

This repo includes the assembly information and bill of material for an Autokit tile, with the following features:

- sd card multiplexing
- power control
- hdmi capture
- ethernet control
- serial
- other usb peripherals

## Contents

- [Autokit assembly and BoM](#autokit-assembly-and-bom)
  - [Contents](#contents)
  - [Nomenclature](#nomenclature)
  - [Bill of Materials](#bill-of-materials)
  - [Assembly](#assembly)
    - [General layout](#general-layout)
    - [Assembling a tile](#assembling-a-tile)
      - [Warnings](#warnings)


## Nomenclature

- DuA - Device under Automation
- BoM - Bill of Materials
- Mux - Multiplexer
- SD Card - Secure Digital Card
- Host - A single board computer, such as a Raspberry Pi 4, that runs the Autokit suite
- Node - A USB-controlled module for interacting with a DuA (connected to a host Autokit)
- Tile - A complete Autokit + DuA instance, including host, nodes, PSU and cables
- PSU - Power Supply Unit

## Bill of Materials

The BoM can be found [here](source/bom/bom.csv)

## Assembly

### General layout

Generally we recommend the following layout of the board:

![block-diagram](documentation/images/panel.jpg?raw=true)

All modules selected, the "host"/"controller" device, and the device under automation (DuA) can be mounted onto the [IKEA Skadis panel](https://www.ikea.com/gb/en/p/skadis-pegboard-white-50320805/#content)

As each DuA will have different locations for the interfaces, and different USB modules may be selected, cable management must be flexible - the location chosen for each module and cable route may be determined by these factors.

We use [velcro cable ties](https://www.amazon.co.uk/Cable-Ties-Reusable-Multi-Purpose-Electronics/dp/B07WPTKD5J/) to secure cables to the board, usually routing behind the board where possible.

Securing the host and DoA to the board may require custom fittings, or longer cable ties.

### Assembling a tile

The following instructions are for assembling a an Autokit tile using the pieces listed in [BoM](#bill-of-materials).
Different instances of these pieces may be used (for example a different USB to Ethernet adapter) - so pictures may not match up.

1. Ensure that the power relay is **disconnected to the mains supply** until the assembly is complete
2. Begin with the empty Skadis board
3. Place the host device in the top right corner of the Skadis board and secure it (with either velcro, zip ties or elastics)
4. Plug one Ethernet cable into the Ethernet port of the host
5. Place the power relay in the bottom right corner of the board. **DO NOT CONNECT TO MAINS POWER**
6. Plug in the C14-to-plug-socket cable into the relay's C13 socket
7. Plug in the USB hub into the host
8. Plug USB-A to USB-B cable from the USB hub to the relay USB-B port
9. Plug the micro-USB cable from the USB-hub to the SD card multiplexer
10. Plug in the USB-Serial adapter into the USB-hub
11. Plug the USB-HDMI adapter to the USB-hub
12. Plug the USB-Ethernet adapter to the USB-hub
13. Place the DuA on left side of the board and secure it (with either velcro, zip ties or elastics)
14. Plug the DuA power supply into plug socket exposed by the C14-to-plug-socket cable then connect this power supply to the DuA
15. Connect the USB-Ethernet adapter to the DuA ethernet port via an ethernet cable. Ignore this is the DuA does not have an Ethernet port. [^1]
16. Connect the USB-HDMI adapter to the DuA via a HDMI cable. Ignore this if is there is no display-out on the DuA.
17. Connect the USB-Serial adapter to the DuA. Ignore this if there is no serial output from the DuA
18. Place an SD card into the SD card multiplexer SD card slot
19. Plug the SD card multiplexer PCB edge connector into the DuA SD card slot.
    1.  If the DuA doesn't have an SD card slot, e.g. if the device boots from a USB drive instead - an SD-USB adapter may be used
    2.  If the DuA is a USBboot device, like the balenaFin - then plug a USB cable from the USB-hub, or the host, to the appropriate USB port on the DuA. [^2]
20. Secure all cables to the board. 
    1. The exact placement is up to the builder and will depend on the exact adapters, cables, cable lengths and DuA; try to organise the placement for ease of maintence
21. Plug the host into mains supply via its own power adapter.
22. Plug the power relay C14 socket to a mains power supply via the C13-to-mains cable. 

**Whenever you want to modify/adjust/change anything on the tile - ensure to disconnect the relay from the mains supply prior to making the change.**

#### Warnings

[^1] Please note that the Ethernet port is used to detect the DuA powered down state, which is used when flashing devices that use a flasher image (e.g Intel NUC)

[^2] Note that to support this, the port must be able to be individually toggled on and off via `uhubctl`. You can check compatibility [on this list](https://github.com/mvp/uhubctl).

When completed, the tile will look something like this:

![tile](documentation/images/autokit-tile.jpg?raw=true)

This setup has an Intel NUC DuA, and uses a UK power adapter and socket.
