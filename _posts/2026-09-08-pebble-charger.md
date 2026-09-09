---
title: Makeshift solution for broken Pebble Time 2 charger
date: 2026-09-08
layout: single
categories: Other
tags:
    - "Electronics"
excerpt: A less than safe fix for a broken Pebble charger
header:
    teaser: "/assets/images/pebble/pic.jpg"
---

My Pebble Time 2 stopped charging today and I figured out the charging dongle that came with the watch somehow broke. The pogo pins (+) and magnets (-) were shorted together when checking with a multimeter. Searching online shows that I am not the first person for this to happen to, and that Pebble support will generally help you out with a new charger. While waiting for that, I opened up the charger and figured the small IC on the board was shorted somewhere, as the 5V and GND pads on the USB C port were not shorted. I cut the traces next to the pogo pins with a knife and checking the test pads indicated the pogo pins and magnets were no longer shorted together. Per the [official hardware "schematic"](https://github.com/coredevices/hardware/blob/main/watch/Pebble%20Time%202%20(obelix)/2026-03-29%20Pebble%20Time%202%20(Obelix)%20Block%20Diagram%20and%20Pinout%20v2.pdf), the watch itself has all the power and battery management circuits and just takes in 5 volts. I soldered a piece of wire between one of the 5V pads and the pogo pins. I was able to successfully charge my watch to full without any issues. 
{% include figure popup=false image_path="/assets/images/pebble/pic.jpg" caption="The 'fix'" %}
I'm not sure exactly what the IC in the charging dongle was for, I believe either to negotiate providing 5V with smart USB C chargers, or to stop output when no watch is detected (or both). I have the dongle plugged into a USB A port so the dongle is constantly outputting 5V when plugged in. I am going to try to remember to connect the dongle to the watch before plugging it in to avoid shorting out on my metal watch band or the watch back. 