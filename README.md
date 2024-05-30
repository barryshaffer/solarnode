# solarnode

This project details the design and construction of a solar-powered Meshtastic node for extended off-grid communication. The node is intended for deployment at the top of an antenna mast for optimal range and signal quality.

## Project Goals

* **Reliable Off-Grid Communication:** Create a robust communication node that can function independently of traditional power sources.
* **Optimized for Antenna Mast Deployment:** Design a system that is compact,lightweight, weather-resistant, and easily installable on an antenna mast. In my case, I'm depolying at the top of a mast comprised of fence top rail that I use to secure the end of my 133'EFHW antenna. The mast isn't very robust so light weight and low wind load were major considerations for my design hence keeping batteries and solar pannel detatched and down at the base of the mast. 


## Components and Materials

* **Meshtastic Device:** [RAK19003 baseboard w/ RAK4631 core module (nRF52840)](https://store.rakwireless.com/products/wisblock-meshtastic-starter-kit?variant=43683420799174)
* **Antenna:** [RAK 5dBi Fiberglass Antenna](https://store.rakwireless.com/products/5dbi-fiber-glass-antenna-supports-863-870mhz?m=3&h=outdoor-antennas)
* **Feedline:** [Ipex to N-type RG178](https://www.amazon.com/gp/product/B0C8M9NR3R/ref=ppx_od_dt_b_asin_title_s03?ie=UTF8&th=1)
* **Solar Panel:** [4W Solar Panel from AliExpress](https://www.aliexpress.us/item/3256803265862880.html?ug_edm_item_id=3256803265862880&pdp_npi=4%40dis%21USD%21%2425.09%21%2424.34%21%21%21%21%21%402101fb1917149664568478412e92d3%2112000025853024091%21edm%21%21%21&tracelog=rowan&rowan_id1=pay_success_20221027_1_en_US_2024-05-05&rowan_msg_id=8350818769920656%249c185f10317945afb7a2615afb1b9b61&ck=in_edm_other&gatewayAdapt=glo2usa) This unit houses the controller and up to 6 18650 cells which would be absolute overkill for the power sipping nRF52 - but if you wanted to throw a bunch of sensors on the RAK or run a more power hungry unit like a T-beam supreme, this pannel should provide plenty of power. 
* **Charge Controller:** Integrated into the solar pannel
* **Battery:** 3 x 3000mAH 18650 lion batteries (rescued/harvested form a bad 4o cell leafblower battery) may still be overkill.
* **Weatherproof Enclosure:** plastic pill box - may change to painted ABS to survive the AZ summers
* **Mounting Hardware:** [Antenna Roll Bar Mount Bracket](https://www.amazon.com/dp/B0B8MS3TMN?psc=1&ref=ppx_yo2ov_dt_b_product_details)
* **Cables and Connectors:** [25ft usb cable](https://www.amazon.com/dp/B0CQ4C2P3V?ref=ppx_yo2ov_dt_b_product_details&th=1),[USB C female socket](https://www.aliexpress.us/item/3256806029053310.html?spm=a2g0o.productlist.main.1.5403UKKPUKKPaI&algo_pvid=dc6a95c7-c578-418e-a764-d21567cb393d&algo_exp_id=dc6a95c7-c578-418e-a764-d21567cb393d-0&pdp_npi=4%40dis%21USD%211.60%211.60%21%21%211.60%211.60%21%402101fb1017170388456027409e790b%2112000036316053016%21sea%21US%214677208350%21&curPageLogUid=LK9XUclQLx3T&utparam-url=scene%3Asearch%7Cquery_from%3A) This may change.

## Assembly and Installation

1. **Wiring:** I replaced the 5x2mm barrel plug on the solar panel with a USB-C socket. This allows me to power the node with a single USB cable, which makes it easier to flash new firmware. I later learned that nRF52 devices can be flashed over Bluetooth, so, if confirmd,  I may change the wiring to a simple 2-conductor wire from the batteries to the RAK battery connector. This would allow me to monitor the battery levels and see how well the panel is doing.  
2. **Enclosure:** The idea here is as small and light as possible, My approach is basically to mount the antenna to the mast and mount the radio direcly to the antenna. Coax is extremely lossy at these frequencies, and meshtastic radios have minuscule power output, so in order to make the most of the hi gain attenna the closer to zero you get with your feed line the better. The shortest connector I found was 4" so that's what I'm using. 
3. **Mast Mounting:** I'm not happy with the 90 degree mount I'm using as it's designed for an NMO connector which is a lot bigger than the N-type on the antenna so I had to use a fender washer to make it secure. I may change the enclosure to something more robust and mout it to the mast with ubolts and mount the antenna to it. Like [this](https://www.lowes.com/pd/CANTEX-1-2-in-Combination-Connector-Schedule-40-PVC-Compatible-Schedule-80-PVC-Compatible-Conduit-Fitting/3274869) for example.

## Configuration and Testing

1. **Meshtastic Setup:** configured to 'router' also added a secondary 'Admin' channel so I can change radio configurations over the mesh since my mast location is out of bluetooth range from my house. **IMPORTANT: do not disable bluetooth to try and save batteries on an nRF52 device** there is a firmware bug that will cause the radio to be unresponsive if bluetooth is disabed. My understanding is that the BT radio goes to sleep anyway so there shouldn't be much power lost keeping it enabled. 
2. **Power Monitoring:** TBD
3. **Range Testing:** TBD

## Photos and Diagrams

* Coming soon

## Additional Notes

* 


