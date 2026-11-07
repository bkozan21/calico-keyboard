# Calico Split Keyboard

This repository contains software and CAD files for a custom wireless split keyboard. I uses ZMK as firmware. The rest of this README is a tutorial about how to make this or a similar keyboard.


# Final product in action

[0001-1000.mp4](Split%20Keyboard/0001-1000.mp4)

# Table of contents

# Introduction

This was a personal project idea. I spent a lot of time during a week in front of a computer typing. Modern keyboards are not that ergonomic. As I was looking for a better keyboard, I came across custom keyboards and decided to make my own.

## Inspiration and Useful Sources

### Main Inspiration

These two videos from Ben Vallack and Christian Selig were my main inspiration. During the design and making of my own keyboard, I went back to these videos quite frequently. If you need more information about something, start with these videos.

[“The REAL Ergonomic Keyboard Endgame!” - How To Design & Make A Totally Custom Keyboard](https://www.youtube.com/watch?v=UKfeJrRIcxw)

[I Built My Dream Keyboard from Absolute Scratch](https://www.youtube.com/watch?v=7UXsD7nSfDY)

Here are the GitHub repositories for the keyboards from the videos above:

[ergogen/input/config-flipper.yaml at master · benvallack/ergogen](https://github.com/benvallack/ergogen/blob/master/input/config-flipper.yaml)

[caldera-keyboard/ergogen/config.yaml at main · christianselig/caldera-keyboard](https://github.com/christianselig/caldera-keyboard/blob/main/ergogen/config.yaml)

### Other useful sources and inspirations

https://www.frandieguez.com/posts/how-to-build-a-split-keyboard-lily58-pro/#putting-all-together

https://github.com/makgyber/kiai-split

https://www.ubiqueiot.com/posts/xiao-nrf52840-zmk

https://github.com/ubiqueIoT/GigaPad/tree/main

This is a very good and detailed tutorial for the ergogen software I used:

[Let's Design A Keyboard With Ergogen v4: Introduction](https://flatfootfox.com/ergogen-introduction/)

[Let's Design A Keyboard With Ergogen v4: Reversible Split Keyboard Tips](https://flatfootfox.com/ergogen-part6-reversible-split/)

# Ingredients

<aside>
ℹ️

You don’t have to buy the items from the links I added. You can use any supplier or store or an equivalent product as long as it is compatible.

</aside>

| Name | Link | Quantity | Notes |
| --- | --- | --- | --- |
| Kailh Low Profile Choc Switches | https://splitkb.com/products/kailh-low-profile-choc-switches?variant=32171144380493&_su_rec=K7XPEFOSKQJ6HuOqu8JvlqgQJot6nW1wtNrVSzVyanA3C1YqsAHD4RuTCrJwP6FZxHm1uhMl3X4t7QNzuMuESyQ1RrEEgi36AF2GOhwYCAo9edE3fmjca5diy_bAAWXqCz8KgsL9PHYvucSHRDPHljyZl6D8sljBpnwmTNCeQKEJPHhKLW_XfV4Vj7vQilxc3kevMZ2U6zh7X3NKLHTFHpHWZRXFbdY0bCzeEJDRBogsHo5YQ6zEQlgKb0bRMkyONT2hpbjF&_su_rec_id=4e69f0e8-41da-4f02-ba84-3d4b565eb13f-1793966067 | 108 | I used 10 brown switches. Those are the arrow keys on both sides. For the red, I used reds. I did this because I was curious of the feeling of the browns. You can mix and match like me or stick to one type. |
| Keycap set | https://splitkb.com/products/mbk-legend-40s-choc-low-profile-keycaps?variant=43111026753795 | 1 | It doesn’t come with enough keycaps for a 108 key keyboard. You need extra keycaps if you have lots of keys. |
| Blank keycaps | https://splitkb.com/products/blank-mbk-choc-low-profile-keycaps?variant=31811487039565 | 56 | It might be a good idea to buy a couple more than you need just in case. Also, in the link I pasted, there are multiple options. I got only “10 x 1u”. That is a pack with ten 1 unit keycaps. |
| Kailh Hotswap Sockets | https://splitkb.com/products/kailh-hotswap-sockets?variant=39472161456205 | 108 | Make sure that you get the “choc” version. They need to match the switches. |
| SMD Diodes | https://splitkb.com/products/smd-diodes?variant=42283984060675 | 108 |  |
| nice!nano Microcontroller board | https://splitkb.com/products/nice-nano?variant=39408154116173 | 2 |  |
| Mill Max Low Profile Sockets | https://splitkb.com/products/mill-max-low-profile-sockets?variant=31945995845709 | 2 | I didn’t like these sockets that much. It is nice that they place the MCU board low but the pins are very thin. It is easy to bend a pin. You can also use a normal male and female headers. |
| JST PH 2 pin Female Socket | https://www.digikey.nl/en/products/detail/jst-sales-america-inc/S2B-PH-K-S/926626 | 2 |  |
| Li-Po battery | https://www.tinytronics.nl/en/power/batteries/li-po/pkcell-li-po-battery-3.7v-150mah-jst-ph-lp402025https://www.tinytronics.nl/en/power/batteries/li-po/pkcell-li-po-battery-3.7v-150mah-jst-ph-lp402025 | 2 | You can use a different capacity one. |
| Small on/off switch | https://www.tinytronics.nl/en/switches/manual-switches/slide-switches/small-switch-for-pcb-or-breadboard | 2 |  |
| Small pushbutton | https://www.tinytronics.nl/en/switches/manual-switches/pcb-switches/tactile-pushbutton-switch-momentary-4pin-6*6*6mm | 2 |  |
| M3 spacer - 10 mm - female to female |  | 22 |  |
| M3 bolt - 10 mm | https://www.tinytronics.nl/en/tools-and-mounting/installation-and-mounting-material/bolts/m3-bolt-10mm-thread-100-pieces | 22 |  |
| M3 bolt - 5 mm | https://www.tinytronics.nl/en/tools-and-mounting/installation-and-mounting-material/bolts/m3-bolt-5mm-thread-100-bolts | 22 |  |
| Rubber feet | https://nl.bauhaus/vilt-meubeldoppen/fix-o-moll-antislip-en-geluiddempers-12-mm/p/20893129 | At least 8 | I used 4 per side but in the 3d models, I added places for more. |

<aside>
⚠️

Be very careful with the LiPo battery. Do not puncture or cut it. Do not short its cables. Otherwise, it might explode and/or cause a fire.

</aside>

<aside>
ℹ️

I call my keyboard “Calico”. (It comes from the cat fur pattern). I don’t exactly know why I chose this name. 

</aside>

<aside>
ℹ️

All the software, 3d files, and the PCB files are on a GitHub repository. You can just use those files if you are making the exact same keyboard or use them as inspiration.

[GitHub - bkozan21/calico-keyboard](https://github.com/bkozan21/calico-keyboard/)

</aside>

# Making the layout (Ergogen)

<aside>
ℹ️

My goal for using ergogen was to generate a PCB layout. If you want to design your own layout, keep reading this section. If you are replicating my design, you can just get the PCB from my GitHub repository and skip to the next section.

https://github.com/bkozan21/calico-keyboard

</aside>

I used a software called ergogen to create the layout of my keyboard. It is a software for creating custom keyboard layouts. It can generate dxf files that you can use for designing a case and more importantly it can automatically generate a KiCad pcb file with the footprints placed according to your design. Then all you have to do is to route the traces. The first link below is the online configurator. The second link is the documentation.

[Ergogen](https://ergogen.xyz/)

[Getting Started | Ergogen docs](https://docs.ergogen.xyz/)

![A screenshot of [ergogen.xyz](http://ergogen.xyz) with my yaml file. On the right are all the output files defined by the yaml.](Split%20Keyboard/Screenshot_20261106_202545.png)

A screenshot of [ergogen.xyz](http://ergogen.xyz) with my yaml file. On the right are all the output files defined by the yaml.

Ergogen takes a yaml file as an input. Here you design where each switch goes. In addition, you can define the board shape, and configure the pcb. You can my final yaml file here: https://github.com/bkozan21/calico-keyboard/blob/main/ergogen_input/calico_ergogen_layout.yaml 

I didn’t start from scratch. Ergogen comes with a couple of examples. I started with the Absolem template. You can learn more about this design here: https://zealot.hu/absolem/. I wanted more keys so I added keys around. I also wanted to make a split keyboard so I deleted the right half. I designed only the left side because the right side is the exact same but mirrored. 

<aside>
✅

If you are designing your own keyboard, a good idea to download the demo.dxf file ergogen generates and print it on an A4. This way you can try your layout in real life. Put your hands on it and see if you like the switch positions.

</aside>

## Main sections in the ergogen yaml file

<aside>
✅

In the online configuratior, you can view the outputs as you are making changes. For example, click on the demo.dxf on the right and it will show you the dxf file. The dxf will change automatically as you are making changes.

</aside>

### Points

```yaml
points:
  zones:
    matrix:
      anchor:
        rotate: 5
        shift: [100, -150]
      columns:
        extra3:
          key.column_net: col1
        extra2:
           key.column_net: col2
...
```

This where the switch placements are made. They are defined as columns and rows. I have three sections. Matrix, thumbfan, and arrows. These are separately defined clusters. `key.column_net` and `row_net` are for assigning PCB nets.

### Outlines

Here, I defined a polygon by specifying points with respect to keys. I used this polygon as the board outline. Using 

### PCB

This is where I defined the footprints to be used in the PCB. You can configure some settings for each footprint. Ergogen supports footprints from the following GitHub repository: https://github.com/ceoloide/ergogen-footprints. For available configuration options look at the files in this repository. You can view the PCB as you are making changes in the online ergogen editor.

![Live preview of the pcb file on ergogen.xyz.](Split%20Keyboard/Screenshot_20261106_212311.png)

Live preview of the pcb file on ergogen.xyz.

Here, you need to think about your columns and rows and how they will connect to the microcontroller board. I have 54 keys per side. The microcontroller doesn’t have 54 pins. This is often the case. There are more keys than the microcontroller pins. That’s why a matrix is used. Columns and rows are actually important. Each key is part of a column and row. It is explained in great detail in the link below. It is best if you just read it instead of me trying to explain it. 

[Let's Design A Keyboard With Ergogen v4: The PCB (Part 3)](https://flatfootfox.com/ergogen-part3-pcbs/)

I used a 9 x 7 matrix. Yes, it is 9 time 7 is 63 and I could have done 6 x 9 which is the exact number of keys I have but I just found it easier to have 7 rows instead of 6. If you look at my layout, there are 9 clear columns. For the arrows and the thumb cluster, I decided to use 2 rows. I just found this easier for routing. 

<aside>
⚠️

The net names for the PCB are created from the row and column names defined under points in the yaml file. Make sure to use different row and column names for the clusters. Otherwise, you will can get switch pads with the same net name even though those pads are not supposed to be the same net (i.e connected).

For example, for the arrow cluster, I initially used “top” for a column and “right” for a “row”. This created a pad name “top_right”. In the main “matrix” cluster, I also had a switch with a “top_right” pad. Those are two different switches. Their pads must not be connected. That’s why I changed the rows and the columns of the arrow cluster to have a “arrows_” prefix such as “arrows_top” and “arrows_right”.

</aside>

For the footprints, make sure that you enable the reversible option. This way the same PCB can be used for both the left and the right side. For example, the hotswap sockets has pads on both sides. This way you can solder a socket to either side. The microcontroller board has these tiny pads next to the pin holes. You can put a solder bridge on those. This way you don’t have to put the microcontroller board upside down on one side. (This is just for esthetic reasons actually. An upside down microcontroller board would look ugly so people came up with this footprint option.)

![The microconroller board footprint up close in the KiCad 3d viewer.](Split%20Keyboard/Screenshot_20261106_215232.png)

The microconroller board footprint up close in the KiCad 3d viewer.

More info here:

[Let's Design A Keyboard With Ergogen v4: Reversible Split Keyboard Tips](https://flatfootfox.com/ergogen-part6-reversible-split/)

# The PCB

<aside>
ℹ️

Again, if you are just replicating my design, you can just use the PCB files in my GitHub repository. If you are designing your own keyboard or making modifications to my design, keep reading this section, otherwise you can skip this section.

https://github.com/bkozan21/calico-keyboard

</aside>

## Finalizing the Design

### Download the PCB file

Once you are done with your layout and you added all the footprints for the PCB in the ergogen yaml file, you can download the PCB from the ergogen online editor. After downloading, I wanted to edit the PCB file because I wanted to add some extra footprints that are not available in ergogen. That’s why I created a new kicad project first and then imported the ergogen generated PCB. I used the “File → Append Board” option. Then I added some extra footprints using “Place → Place Footprints”

### Add missing components

I added a regular three pin header (`PinHeader_1x03_P2.54mm_Vertical`) because that was the footprint of the on/off switch I used. Then I added a classic push (`SW_PUSH_6mm`)button for the microcontroller board reset. I noticed that using the schematic is not necessary. You can just click on a pad (sometimes you may need to click multiple times, otherwise you select the whole component) and change the net assignment in the properties panel. You can select from an existing net or create a new net.

![Editing the net assignment of a pad in KiCad.](Split%20Keyboard/Screenshot_20261106_220724.png)

Editing the net assignment of a pad in KiCad.

<aside>
⚠️

I had to change the pad assignment for the battery connector because it was the opposite of the battery I used. Check you batter connector and see which side is the positive and which side is the negative side. Update the footprint if necessary. Keep in mind which side you are going to place the JST battery connector. In my design, the JST batter connector goes to the bottom (same side as the hotswap sockets and the diodes)

</aside>

<aside>
⚠️

I also added another footprint. It has a circle in the silkscreen layer and 8 pins. This is for a joystick I planned to add. It is for mouse input. I didn’t have time to implement this feature so you can ignore this component.

</aside>

After placing the components, you can also add some logos or text in the silkscreen layers.

### Routing

If the previous steps are completed correctly, every pad must now have a net name. Now you need to route traces and connect the each pad where it needs to be connected. Don’t forget, there are two copper layers. You can switch between layers with vias. I used the default trace width of 0.25 mm and the default vias with diameter of 0.8 mm and a hole of 0.4 mm.

![Screenshot_20261106_221415.png](Split%20Keyboard/Screenshot_20261106_221415.png)

### Design Rule Check (DRC)

I planned to order the PCBs from JLCPCB. That’s why I wanted to add design rules so that I can check if my design is within their manufacturing capabilities. That’s why I added custom design rules that were created specifically according to the JLCPCB capabilities. I got these rules from a GitHub repository: https://github.com/Cimos/kicad-druid/blob/main/JLCPCB/JLCPCB-2L-1oz.kicad_dru You can add these rules in KiCad PCB view. Go to “File → Board Setup → Custom Rules” and copy and paste the contents of the file with the design rules.

Now, you can run the DRC with the custom rules. Go to “Inspect → Design Rules Checker” and click on the “Run DRC” button. I got errors for the pads of the JST1 battery connector. I ignored those. The PCB turned out fine. I also ignored the warnings. 

![I ignored the errors on the JST1 footprint.](Split%20Keyboard/Screenshot_20261106_222641.png)

I ignored the errors on the JST1 footprint.

## Ordering the PCB

### Generate Gerber Files

These files are needed by the manufacturer. Again, you can find the ones I used in my GitHub repository. To generate: 

1. Go to “File → Plot”.
2. Select an output directory.
3. Click on “Generate Drill Files”
4. Click on “Generate” on the new window and then click “close”
5. Click on “Plot” and then close.
6. Now compress the output directory into a zip file. This is the file you need to upload to JLCPCB.

### Order from a manufacturer

I used JLCPCB. You need to upload the gerber file and select some options. Here are all the options I selected:

```
Gerber file: output2_Y2

Build Time: 24 hours

Base Material: FR-4

Layers: 2

Dimension: 218.7 mm* 151.6 mm 218.71mm* 151.6mm

PCB Qty: 5

Product Type: Industrial/Consumer electronics

Different Design: 1

Delivery Format: Single PCB

PCB Thickness: 1.6mm

Specify Stackup: no

PCB Color: Green

Silkscreen: White

Material Type: TG135

Via Covering: Tented

Surface Finish: LeadFree HASL

Deburring/Edge rounding: No

Outer Copper Weight: 1 oz

Gold Fingers: No

Electrical Test: Flying Probe Fully Test

Castellated Holes: no

Edge Plating: No

Mark on PCB: Remove Mark

Blind Slot: No

Min via hole size/diameter: 0.3mm/(0.4/0.45mm)

Via Plating Method: Not Specified

4-Wire Kelvin Test: No

Paper between PCBs: No

Appearance Quality: IPC Class 2 Standard

Confirm Production file: No

Silkscreen Technology: Ink-jet Printing Silkscreen

Package Box: With JLCPCB logo

Inspection Report: No

Board Outline Tolerance: ±0.2mm(Regular)

Impedance Test Report: No

UL Marking: No

Countersink Hole: No

Humidity Indicator Card: No

Shortage Preference: Require Full Quantity

Weight: 0.7kg
```

I used “DHL Express (DDP)” as my shipping option. This shipping option handles the customs duties and taxes. I paid around 6 euros for 24-hour manufacturing. I ordered the PCBs on Saturday evening, and I picked the package up on Friday evening from a DHL point.

## Soldering

There is nothing unique about soldering the parts. Follow general advice. Make sure to apply flux. I will still give some tips and points to take into account.

<aside>
⚠️

Don’t forget to flip the PCB when doing the other side.

</aside>

![Left side bottom](Split%20Keyboard/IMG_8378.jpeg)

Left side bottom

![Both sides bottom](Split%20Keyboard/4FD74FD7-B189-43E3-9BA2-1D0F7D2AF989.jpeg)

Both sides bottom

![A hotswap socket and a diode up close](Split%20Keyboard/IMG_8463.jpeg)

A hotswap socket and a diode up close

### Hotswap Sockets

The way I soldered hotswap sockets is as follows. I put the socket on the pads. Made sure that it is flush with the PCB and flat. I soldered one leg onto its pad. I didn’t immediately took the soldering iron away. After putting solder, I kept the iron on the pad to keep the solder still melted. Then I pushed on the socket with a pair of tweezers to make sure that it was flat and fully up against the PCB. Then while pushing with the tweezers, I pulled the soldering iron away. After a second or two, I stopped pushing with the tweezers. I did this because when soldering the first leg, the socket might lift up. The push with the tweezers makes sure that the socket is flat at the end of the soldering process. After soldering the first leg, I soldered the second leg as usual. 

![A soldered socket](Split%20Keyboard/IMG_8458.jpeg)

A soldered socket

![A soldered socket from the front](Split%20Keyboard/IMG_8476.jpeg)

A soldered socket from the front

![IMG_8479.jpeg](Split%20Keyboard/IMG_8479.jpeg)

![IMG_8475.jpeg](Split%20Keyboard/IMG_8475.jpeg)

### Diodes

Diodes have direction. It matters which way you solder them! They are marked with a line on one side. The diode pads are marked with a silkscreen. Make sure the lines match! The text and the line on a diode can be difficult to see. Try looking at the diode from different angles. In certain angles, the markings are easy to read and from other angles, they are difficult to read.

![IMG_8486.jpeg](Split%20Keyboard/IMG_8486.jpeg)

Here, a diode is placed next to its pads. It is not soldered! It is not very clear, but towards the right side, you can see a line. The diode symbol on the silkscreen also has a line towards the right.

![IMG_8459.jpeg](Split%20Keyboard/IMG_8459.jpeg)

A properly soldered diode. Here, you can see the line on the right more clearly.

The way I soldered the diodes is as follows:

1. Place some solder (with the soldering iron) on one of the pads on the PCB.
2. Hold the diode with a pair of tweezers in one hand.
3. Hold the soldering iron with your other hand.
4. Heat the solder on the PCB,
5. Push one leg of the diode into the melted solder.
6. Remove the soldering iron while holding the diode in place.
7. Solder the other leg of the diode normally.

![IMG_8462.jpeg](Split%20Keyboard/IMG_8462.jpeg)

![IMG_8482.jpeg](Split%20Keyboard/IMG_8482.jpeg)

These SMD diodes are tiny. Use a pair of tweezers with very thin tips.

### The microcontroller board

First, solder the female sockets. Then put the microcontroller on top of the sockets and insert the pins through the microcontroller board into the sockets. Be very careful and gentle. The pins can bend easily. Once the pins are pushed down fully, you can solder them to the microcontroller board. 

![IMG_8493.jpeg](Split%20Keyboard/IMG_8493.jpeg)

Then, you need to put solder bridges to the pads on the other side of the PCB. 

![IMG_8466.jpeg](Split%20Keyboard/IMG_8466.jpeg)

![IMG_8467.jpeg](Split%20Keyboard/IMG_8467.jpeg)

I put some hot glue on top of the battery terminals just to have some extra protection against shorts.

![IMG_8493.jpeg](Split%20Keyboard/c1b9ab7c-c92d-442f-b93a-297ae2ea4967.png)

Solder the rest of the components similarly.

# The Case

<aside>
ℹ️

The STLs are also on my GitHub repository.

https://github.com/bkozan21/calico-keyboard

</aside>

I designed the case in Onshape. I made the document public. You can view it here:

[Onshape](https://cad.onshape.com/documents/db90108e0c18a49f77f814f0/w/d8d8382bf78da29ebfbabf1b/e/875cb3c507a1a049483ec79f?renderMode=0&uiState=6aee2f85786fe483e2490886)

You need to 3d print the case parts. The case for one side consists of one top layer, one bottom layer, and 11 spacers. The 3d files are designed for the left side. For the right side, you can mirror the top and bottom layers in the slicer. The spacers are discs. They don’t need to be mirrored.

![Recommended print orientation for the top layer.](Split%20Keyboard/Screenshot_20261106_232448.png)

Recommended print orientation for the top layer.

![Recommended print orientation for the bottom layer.](Split%20Keyboard/Screenshot_20261106_232548.png)

Recommended print orientation for the bottom layer.

I used 100% infill for the top layer and the spacers. I used 15% infill for the bottom layer. I used normal PLA for everything. I used the original Prusa i3 MKS3S+ printers with a 0.8 nozzle in the TU Delft Science Centre. I printed everything with 0.40 mm layer height. The top layer requires a little bit of support around the microcontroller. I used tree supports in the Prusa slicer. They came of relatively easily.

<aside>
⚠️

Depending on the printer you use, you might need to adjust the tolerances in the 3d models.

</aside>

<aside>
⚠️

I added a small inset in the bottom plate for the battery, but I ended up not using it. After removing supports, it was still rough. Just connecting the battery to the socket was enough for me.

</aside>

![IMG_8234.jpeg](Split%20Keyboard/IMG_8234.jpeg)

# Assembly

<aside>
⚠️

Be very careful with the LiPo battery. Do not puncture or cut it. Do not short its cables. Otherwise, it might explode and/or cause a fire.

</aside>

1. Make sure the power switch is in the off position and plug in the battery.
2. Put the PCB into the top layer. The microcontroller must face up.

![IMG_8379.jpeg](Split%20Keyboard/IMG_8379.jpeg)

1. Put a 10 mm M3 bolt through the mounting holes and the PCB. Then put a 3d printer spacer and a 10 mm M3 spacer.

![The black piece under the brass M3 spacer is a 3d printer spacer.](Split%20Keyboard/IMG_8380.jpeg)

The black piece under the brass M3 spacer is a 3d printer spacer.

1. Put the bottom layer 3d print and attach it with 5 mm M3 bolts.

![IMG_8496.jpeg](Split%20Keyboard/IMG_8496.jpeg)

![IMG_8383.jpeg](Split%20Keyboard/IMG_8383.jpeg)

1. Stick the rubber feet to their insets.

![IMG_8381.jpeg](Split%20Keyboard/IMG_8381.jpeg)

1. Attach keycaps to the switches. (I did this first because I noticed that keycaps require a lot of force to attach. When you place the switches first, you apply the force to the PCB when attaching a keycap. I didn’t want to apply a lot of force to the PCB,
2. Put switches into the sockets.

![IMG_8277.jpeg](Split%20Keyboard/IMG_8277.jpeg)

![IMG_8278.jpeg](Split%20Keyboard/IMG_8278.jpeg)

![IMG_8373.jpeg](Split%20Keyboard/IMG_8373.jpeg)

![IMG_8375.jpeg](Split%20Keyboard/IMG_8375.jpeg)

# Configuring the software

<aside>
ℹ️

If you are replicating my design, go to the downloading the firmware section.

</aside>

<aside>
ℹ️

Please refer to my GitHub repository. I didn’t put everything here to make this tutorial easier to follow.

https://github.com/bkozan21/calico-keyboard

</aside>

For the software, I used ZMK. It is an open-source keyboard software that supports wireless split keyboards.

[Hello from ZMK Firmware | ZMK Firmware](https://zmk.dev/)

<aside>
ℹ️

I performed these operations on a computer running Ubuntu 24.04.5 LTS. If you are trying this on Windows and run into issues, you can try using the Windows Subsystem for Linux. 

</aside>

1. Create a GitHub account if you don’t have one. https://github.com/
2. Download the ZMK CLI. For that, follow the steps here, from start until **`Config Repo Setup`**
    
    [Installing ZMK | ZMK Firmware](https://zmk.dev/docs/user-setup?operating-system=linux#prerequisites)
    
    When you are done, run `zmk --version` on your terminal. If everything went well, this command should print a version number such as `0.5.0`.
    
3. Now, it is time to create a repository for the firmware files for the macro pad. Change directory to a place where you would like to store the firmware files. There will be a new folder created here automatically.
    
    ```bash
    cd ~/Documents
    ```
    
4. Now run `zmk init` 
    
    You will see two options. You can use up and down arrows to select an option. Select `Create a new ZMK config repo` and hit enter.
    
5. It will display a text about creating a repository. Here, once you hit enter, it will open a webpage to create a GitHub repository.

![Screenshot_20261002_144008.png](Split%20Keyboard/Screenshot_20261002_144008.png)

Here, you can change the repository name. If you want, you can set the visibility to private. Then scroll down and click `Create Repository`.

1. Now, you need to copy the repository URL and past it to the terminal. You will find the repository URL when you click on the green `Code` button. Depending on how you authenticated with the GitHub CLI, use either the HTTPS URL or the SSH URL. (You can try both. If one doesn’t work, try the other one)

![Screenshot_20261002_144158.png](Split%20Keyboard/Screenshot_20261002_144158.png)

![Screenshot_20261002_144539.png](Split%20Keyboard/Screenshot_20261002_144539.png)

Hit enter. You can then enter a folder name if you want or leave it default by hitting enter again. At the end, a folder with ZMK project files will be created. If it says “Would you like to add a keyboard now?” Enter `n` and hit enter. We will not add a keyboard, we will create a new one.

1. Change directory to the newly created folder and run `zmk keyboard new`. 
    1. Enter the name of the keyboard, then pick an abbreviated name, then an ID. Try to make these similar to each other. 
    2. Select `shield` as the keyboard type. 
    3. Select `pro_micro` as the interconnect. (The nice_nano microcontroller we use has the same pin layout as a pro_micro)
    4. Select `split` as the keyboard layout.
2. Open the folder in Visual Studio Code. (You can use any text editor, but I find VS Code nice)
3. Add these lines to `build.yaml`:
    
    ```yaml
    include:  
      - board: nice_nano_v2    
        shield: calico_left
      - board: nice_nano_v2    
        shield: calico_right
    ```
    
    I named my keyboard “calico”. That’s why I wrote “calico_left” and “calico_right”. You an use the name of your keyboard.
    
4. Now, go to `/boards/shilds/<name of your keyboard>/` 

<aside>
ℹ️

I left some files as they are. I modified some files. If you are using a different microcontroller or doing something different than I did, you may need to configure your software files differently. In addition, if you want some different behaviour, you might need to change these configuration files. Refer to the ZMK docs. Below is the page about adding a new keyboard to ZMK.

[New Keyboard Shield | ZMK Firmware](https://zmk.dev/docs/hardware-integration/new-shield)

</aside>

1. Leave `Kconfig.defconfig` as it is.
2. Leave `Kconfig.shield` as it is.
3. Edit `<name of your keyboard>-layouts.dtsi` 
    1. Add  row-gpios. Note: Here, you need to use pro micro pin numbers. Refer to the image below. They need to be set as `(GPIO_ACTIVE_HIGH | GPIO_PULL_DOWN)`
    2. Define a default transform. Here, the number of columns needs to be defined as twice as many as the actual columns on one side. You configure ZMK as if your keyboard is one piece instead of two separate pieces.
    3. Define a map. Here you define where each switch is (i.e which row and column). My matrix doesn’t have switches in certain locations. I skipped those switches. That’s why there are gaps in my map.
4. Edit `<name of your your keyboard>_left.overlay` and `<name of your your keyboard>_right.overlay` :
    1. Add col-gpios here. Note: The order of the col-gpios for the right side must be the opposite of the left side.
    2. Define a coll offset for the right side. This must be the number of columns you have on one side. Here, we are basically telling ZMK to look at the right half of the keymap.
5. Add the following lines to `<name of your keyboard>.conf` :

```
CONFIG_ZMK_SLEEP=y
CONFIG_BT_CTLR_TX_PWR_PLUS_8=y
CONFIG_ZMK_KEYBOARD_NAME="calico-keyboard"
CONFIG_ZMK_HID_CONSUMER_REPORT_USAGES_BASIC=y
```

1. Configure the keymap by changing `<name of your keyboard>.keymap`
    
    <aside>
    ℹ️
    
    Refer to ZMK documentation for details:
    
    https://zmk.dev/docs/keymaps
    
    https://zmk.dev/docs/keymaps/list-of-keycodes
    
    </aside>
    
2. Edit `<name of your keyboard>.zmk.yml`:
    1. Remove the studio option from features because we are not going to use it.
3. After you are done with changing the files, commit and push your changes.
    
    <aside>
    ℹ️
    
    You don’t need to know how to use git to follow this tutorial but it might be nice to be familiar with it to understand what is going on. Here you can read about git: https://www.geeksforgeeks.org/git/git-tutorial/
    
    </aside>
    
    You can use the built-in VS Code version control tools to commit and push or you can use the command line
    
    1. Stage all your changes. With this command, you mark all your changes as ready to be committed.
        
        ```bash
        git add .
        ```
        
    2. Commit your changes. With this command, you record your changes. The text in quotes is the commit message. This is a short note that describes what the commit achieves. You can write whatever makes sense to you.
        
        ```bash
        git commit -m "initial board files"
        ```
        
    3. Push your changes. With this command, all your local commits are sent to the server. In this case, it is GitHub.

# Download the firmware

<aside>
ℹ️

If you are replicating my design, just go to the release v1.0.0 and download the `firmware.zip` file. You can find the link to that release here:

[Release v1.0.0 · bkozan21/calico-keyboard](https://github.com/bkozan21/calico-keyboard/releases/tag/v1.0.0)

If you made your own design, keep reading.

</aside>

When you push, a GitHub action is triggered that will build the firmware. This is set up through the ZMK template that the repository is based on. Click on `Actions` in the repository. It shows all the triggered actions.

![Screenshot_20261002_152849.png](Split%20Keyboard/Screenshot_20261002_152849.png)

<aside>
ℹ️

 If an action fails, it shows up as a red cross. You can enter and see the output text. Based on the error messages in the output, you can fix the issue locally, commit, and push. A new action will be triggered.

For example, in a different project repository, I made a typo in the build.yaml. Here, you can see that it says `No board named 'seeduino_xiao_ble'` . It should have been `seeeduino_xiao_ble` with one more ‘e’.

![Screenshot_20261002_153157.png](Split%20Keyboard/Screenshot_20261002_153157.png)

</aside>

Go to the latest action. Make sure that it was successful. It should appear with a green tick. Scroll down to the Artifacts section. There is the firmware. Download it and unzip it.

![Screenshot_20261002_153429.png](Split%20Keyboard/Screenshot_20261002_153429.png)

There should be two .uf2 files in the unzipped folder. One firmware file for each side.

![Screenshot_20261107_002258.png](Split%20Keyboard/Screenshot_20261107_002258.png)

# Flash the firmware

1. Connect the left side’s microcontroller (nice_nano) board to your computer with a USB-C cable. 
2. Double-click the reset button (It is on the PCB).  The microcontroller will show up on your laptop as a USB flash drive.
3. Copy the .uf2 file for the left side and paste it to the flash drive that appeared. When the transfer is complete, you might get an error. This is fine. I think the microcontroller board automatically disconnects. 
4. Repeat all the steps above for the right side.

# Connecting to a device

Set the switch to the on position on both sides. Now, you should be able to find the keyboard as a Bluetooth device and connect to it. It shows up with the name you set during the initial setup. You will only see one Bluetooth device. The right side communicates with the left side. The left side communicates with your Bluetooth device.

![Screenshot_20261107_003531.png](Split%20Keyboard/Screenshot_20261107_003531.png)

Once it is connected, it works like a normal Bluetooth keyboard. Once you have it paired with a computer, every time you turn on the keyboard, it will automatically connect to that computer.

<aside>
✅

Congrats. If you reached this point, this means you have your own custom wireless split keyboard.

</aside>