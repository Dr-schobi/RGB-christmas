# RGB-christmas

Around Christmas 2020/21 Matt Parker published  a tree from RGB pixels and started 3D mapping and software development
https://www.youtube.com/watch?v=v7eHTNm1YtU and 
https://www.youtube.com/watch?v=TvlpIojusBE

This was a good inspiration, but I wanted to change a few things:

- different lights: the chunky RGB pixels and thick cables seemed outdated. The Chinese manufacturer BTF Lighting makes much nicer [RGB led lights](https://www.btf-lighting.com/collections/led-strip-set/products/usb-rgb-led-pixels-string-christmas-lights-2m-5m-10m-rf-21keys-controller-ws2812b-ic-addressable-individually-light-10-leds-m-5v) available through Aliexpress. A first test showed that they could provide acceptable appearance for the main living room tree.
- different software: the [WLED project](https://kno.wled.ge/) enables the quickest possible operation, many effects, while being easily extendable. I already had some ESP8266 modules available


## Construction and Setup

The main challenge is the high current on the 5V rail. The LED strings need additional power injection every 50 or 100 LEDs.
This is solved by a central 24V power supply and a lot of DC-DC converters that generate 5V somewhere on the tree.


Components:
- over 20 packs of LED strings of BTF Lighting fairy pixel LED strings, 50 LEDs per string
- adjustable output DC-DC converters for point of load supply, converting from 24V distribution to 5V insertion at string connections
- an 80W 24V Meanwell power supply (already available)
- Phoenix Contact PTFIX 12x distribution blocks for easy wiring
- 200mA fuses and wired fuse holders in each distribution wire
- 2 pin and 3 pin male/female JST connectors with attached cables
- about 75m of 2x0.35mm^2 wire for 24V power distribution, this was cheap aluminium wire. Testing showed little resistive heating at 24V 
- black heat shrink to hide most of the DC-DC converters



## Required fixing

Some things did not go as planned
- the lab setup was runing fine for a few weeks, but the tree started to flicker
  - I added a quick-fix to the voltage level problem as described here https://hackaday.com/2017/01/20/cheating-at-5v-ws2812-control-to-use-a-3-3v-data-line/
  - an LED in the middle of a string broke and flickering started at this LED - I cut it out and reconnected the wires, (soldering and transparent heat shrink)
  - some faults can be attributed to the cheap JST connectors and went away with reseating the plugs

- in the lab setup one of the strings had the output connectors with a different pin ordering, shorting my power supplies and buring a few fuses
- one of the point-of-load regulators broke

