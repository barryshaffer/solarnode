# solarnode

This project details the design and construction of a solar-powered Meshtastic node for extended off-grid communication. The node is intended for deployment at the top of an antenna mast for optimal range and signal quality.

## Project Goals

* **Reliable Off-Grid Communication:** Create a robust communication node that can function independently of traditional power sources.
* **Optimized for Antenna Mast Deployment:** Design a system that is compact,lightweight, weather-resistant, and easily installable on an antenna mast. In my case, I'am depolying at the top of a mast comprised of fence top rail that I use to secure the end of my 133'EFHW antenna. The mast isn't very robust so light weight and low wind load were major considerations for my design. 


## Components and Materials

* **Meshtastic Device:** [RAK19003 baseboard w/ RAK4631 core module (nRF52840)](https://store.rakwireless.com/products/wisblock-meshtastic-starter-kit?variant=43683420799174)
* **Solar Panel:** [4W Solar Panel from AliExpress](https://www.aliexpress.us/item/3256803265862880.html?ug_edm_item_id=3256803265862880&pdp_npi=4%40dis%21USD%21%2425.09%21%2424.34%21%21%21%21%21%402101fb1917149664568478412e92d3%2112000025853024091%21edm%21%21%21&tracelog=rowan&rowan_id1=pay_success_20221027_1_en_US_2024-05-05&rowan_msg_id=8350818769920656%249c185f10317945afb7a2615afb1b9b61&ck=in_edm_other&gatewayAdapt=glo2usa) This unit houses the controller and up to 6 18650 cells.
* **Charge Controller:** Integrated into the solar pannel
* **Battery:** 3 x 3000mAH 18650 lion batteries (rescued/harvested form a bad 4o cell leafblower battery) This may be overkill as the nRF52 sips power.
* **Weatherproof Enclosure:** plastic pill box - may change to painted ABS to survive the AZ summers
* **Mounting Hardware:** [Antenna Roll Bar Mount Bracket](https://www.amazon.com/dp/B0B8MS3TMN?psc=1&ref=ppx_yo2ov_dt_b_product_details)
* **Cables and Connectors:** [25ft usb cable](https://www.amazon.com/dp/B0CQ4C2P3V?ref=ppx_yo2ov_dt_b_product_details&th=1),[USB C female socket](https://www.aliexpress.us/item/3256806029053310.html?spm=a2g0o.productlist.main.1.5403UKKPUKKPaI&algo_pvid=dc6a95c7-c578-418e-a764-d21567cb393d&algo_exp_id=dc6a95c7-c578-418e-a764-d21567cb393d-0&pdp_npi=4%40dis%21USD%211.60%211.60%21%21%211.60%211.60%21%402101fb1017170388456027409e790b%2112000036316053016%21sea%21US%214677208350%21&curPageLogUid=LK9XUclQLx3T&utparam-url=scene%3Asearch%7Cquery_from%3A) This may change.

## Assembly and Installation

1. **Wiring:** About the only wiring I did was to replace the 5x2mm barrel plug coming out of the solar pannel with a usb c type socket so that I only have to run a single usb cable down the mast. Usb allows and option to flash new firmware without pulling the down off the mast. - I have since learned (but not confirmed) that nRF52 devices support flashing over bluetooth. So my wiring could change to a simple 2 conductor wired straight from the batteries in the solar pannel to the battery connector of the RAK. It does seem silly to take a 3.6V battery buck boost it up to 5V then have the RAK convert it back down to 3.3v for the Radio. I do like the thought of that approach since it will let me monitor the battery levels and see how well the pannel is doing.  
2. **Enclosure:** Mount the components inside the weatherproof enclosure, ensuring proper ventilation and secure connections.
3. **Mast Mounting:** Attach the enclosure to the antenna mast using appropriate hardware. Consider the weight distribution and wind resistance for stability.

## Configuration and Testing

1. **Meshtastic Setup:** Configure the Meshtastic device for your desired network settings (channels, frequencies, etc.).
2. **Power Monitoring:** Observe the battery voltage and charging status to ensure the solar panel is providing adequate power.
3. **Range Testing:** Test the communication range of the node in various conditions (weather, obstructions).

## Photos and Diagrams

* Include clear photos of your completed node from different angles.
* If possible, provide a wiring diagram to illustrate the connections between components.

## Additional Notes

* Discuss any challenges you faced during the build process and how you addressed them.
* Offer suggestions for alternative components or design modifications.
* Share your experiences with the node in real-world use.


