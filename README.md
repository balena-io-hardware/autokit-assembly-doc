# Autokit assembly and BoM

This is the assembly information and BoM for the autokit suite

## Supported USB Module list

The following lists all supported pieces of hardware for the autokit. One of each piece is required for the complete assembly - however not all pieces may be used for a given application. You can pick and choose which pieces you need.

### USB hubs

- [Anker 4 port usb hub](https://www.amazon.co.uk/Anker-4-Port-Macbook-Surface-Notebook/dp/B00Y25XFGK/ref=sr_1_3?keywords=usb+hub&qid=1660905847&sr=8-3)

### SD card multiplexors

- [Autokit SD Mux](https://github.com/balena-io-hardware/autokit-sdMux-pcb)
- [Linux Automation GmbH](https://shop.linux-automation.com/usb_sd_mux-D02-R01-V02-C00-en)
- [Tizen SDWire](https://3mdeb.com/shop/open-source-hardware/sdwire/)

### Power relay

- [Autokit Relay](https://github.com/balena-io-hardware/autokit-relay-3d)

### Serial

- [FTDI UART to USB cable](https://uk.rs-online.com/web/p/raspberry-pi-cables/7676200)

### Ethernet adapter

- [Amazon basics Ethernet to USB adapter](https://www.amazon.co.uk/AmazonBasics-1000-Gigabit-Ethernet-Adapter/dp/B00M77HMU0) 

### HDMI capture

- [Any USB capture device that uses V4l drivers](https://www.amazon.co.uk/MBMT-Streaming-Conferencing-Broadcasting-Compatible/dp/B095P2D745/ref=sr_1_10?crid=3SPJB63MFETVN&keywords=hdmi+capture+linux&qid=1660904596&sprefix=linux+hdmi%2Caps%2C81&sr=8-10) 

## Enclosure

All modules selected, the "host"/"controller" device, and the device under automation (DuA) can be mounted onto an [IKEA Skadis panel](https://www.ikea.com/gb/en/p/skadis-pegboard-white-50320805/#content)

As each DuA will have different locations for the interfaces, and different USB modules may be selected, cable management must be flexible - the location chosen for each module and cable route may be determined by these factors. 

We use [velcro cable ties](https://www.amazon.co.uk/Cable-Ties-Reusable-Multi-Purpose-Electronics/dp/B07WPTKD5J/ref=asc_df_B07WPTKD5J/?tag=googshopuk-21&linkCode=df0&hvadid=375498143972&hvpos=&hvnetw=g&hvrand=685419692277955077&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=1006786&hvtargid=pla-818784109651&psc=1&tag=&ref=&adgrpid=76297946145&hvpone=&hvptwo=&hvadid=375498143972&hvpos=&hvnetw=g&hvrand=685419692277955077&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=1006786&hvtargid=pla-818784109651) to secure cables to the board, usually routing behind the board where possible. 

Securing the host and DoA to the board may require custom fittings, or longer cable ties.

### General layout

Generally we recommend the following layout of the board:
![block-diagram](documentation/images/panel.jpg?raw=true)

