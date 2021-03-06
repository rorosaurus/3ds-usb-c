# Prep

Your PCBs might arrive with some [slight perforations, from the breakaway panelization design](https://github.com/rorosaurus/gba-sp-usb-c/blob/master/images/breakaway-perforations.jpg) during PCB manufacturing. These can be left alone, or optionally filed/sanded away.

The half-circle pad(s) behind the USB-C connector might have some debris across it. You can safely clear that away with a toothpick or similar - that will make it easier to solder to later.

# Test before you install!

I test every board before shipping, but you should be certain it still works before you install it! Plug it in to a ````Type-C <-> Type-C```` cable and USB-C power source. **Do not perform this test with a ````Type-A -> Type-C```` cable - that cable won't verify the board works for full USB-C!** Use a multimeter to measure the voltage across any of the grounded holes and the +5V half-circle in the back. Ensure it reads ~5V. Flip your USB-C cable the other way around and verify it still reads 5V! Alternatively, if you have a USB-C multimeter [like this](https://smile.amazon.com/gp/product/B07X3HST7V/) you can simply plug into that and read the display.

# Instructions

## A note on the charging dock contacts

I recommend abandoning the charging dock contacts if you install this mod. The USB-C port is ~8.8mm wide, the charging dock contacts are ~9.8mm apart. That means, properly centered, you'd have 0.5mm of plastic/prayers in-between your 5V dock contact and the grounded USB-C port frame. I personally don't want to deal with that likely short-circuit, but it might technically be possible if you are super careful and passionate about keeping the charging dock contacts. Make sure you harvest the contacts as you remove the standard charging port, and you'll need to modify the 3D printed bezel to accommodate those charging contacts.

## Step 1: Disassemble your 3DS XL and remove the motherboard

You can follow [this iFixit guide](https://www.ifixit.com/Guide/Nintendo+3DS+XL+Motherboard+Replacement/25399) for good disassembly instructions.

## Step 2: Remove the existing charge port

IMO, this is the hardest part by far. I found it easiest to solder-suck / wick the charging dock contacts first, then remove them.

![Removing charging dock contacts](https://github.com/rorosaurus/3ds-xl-usb-c/blob/master/images/removing-charging-dock-contacts.jpg)

Then I broke off and removed the charging dock contacts plastic support.

![Removing charging dock plastic](https://github.com/rorosaurus/3ds-xl-usb-c/blob/master/images/removing-charging-dock-plastic.jpg)

Then I was able to solder-suck / wick the charging port itself and remove it. I should have been more patient to avoid damaging the pads a little bit.

![Removed charging port](https://github.com/rorosaurus/3ds-xl-usb-c/blob/master/images/removed-charging-port.jpg)

## Step 3: Prepare the new charge port

Assemble (and test!) the new USB-C charge port. That means positioning and soldering the brace into the perfect place, and adding the USB-C port and resistors if your mod came unassembled.

![Unassembled PCB](https://github.com/rorosaurus/3ds-xl-usb-c/blob/master/images/unassembled-pcb.jpg)

Add some solder to sandwich the brace and the main PCB, lining the brace up flat with the edge of the main PCB, like this:

![Assembled PCB bottom](https://github.com/rorosaurus/3ds-xl-usb-c/blob/master/images/assembled-pcb-bottom.jpg)

Ensure it fits well into the slot left by the old charging port.

![Assembled PCB bottom alignment](https://github.com/rorosaurus/3ds-xl-usb-c/blob/master/images/assembled-pcb-bottom-alignment.jpg)

Add your USB-C port and resistors if they aren't there already.

![Assembled PCB top](https://github.com/rorosaurus/3ds-xl-usb-c/blob/master/images/assembled-pcb-top.jpg)

Ensure that your USB-C PCB and the motherboard are flat and flush before continuing.

## Step 4: Position and attach the new charge port

It should align like this, with holes lining up with the motherboard pads underneath.

![Assembled PCB top alignment](https://github.com/rorosaurus/3ds-xl-usb-c/blob/master/images/assembled-pcb-top-alignment.jpg)

Solder each hole, ensuring you heat up the pad underneath and allow solder to flow into the hole, securing the USB-C PCB to the motherboard at each of the 4 holes. Then finally use solder to attach the final half-circle pad to the 5V motherboard pad beneath it.

![New charging port attached](https://github.com/rorosaurus/3ds-xl-usb-c/blob/master/images/new-charging-port-attached.jpg)

## Step 5: Case trimming

Use a dremel, sandpaper, and flush cutters to trim the case to fit the new port width. In my case, I chose to absorb the charging dock contacts as well, then fill it in with a 3D printed bezel.

![After no bezel](https://github.com/rorosaurus/3ds-xl-usb-c/blob/master/images/after-no-bezel.jpg)

## Step 6: 3D Print bezel to fill the gap

[3DS-XL-USB-C-3D-printable-bezel.stl](https://github.com/rorosaurus/3ds-xl-usb-c/blob/master/3DS-XL-USB-C-3D-printable-bezel.stl) is a 3D printable file that you can print/modify to fill in the remaining gap left by this USB-C mod.

![After with bezel](https://github.com/rorosaurus/3ds-xl-usb-c/blob/master/images/after-with-bezel.jpg)

# Troubleshooting

### Did you test the board before installing?

See above instructions! It's critical that you test this to ensure it was not damaged during shipping!

### Try with a different cable and/or charger

This mod should work with all combinations of cables and chargers, but try a different one to help diagnose the problem by eliminating variables.

### Flip the USB-C cable to the other orientation

If it works only in one orientation, then check the two small resistors. Ensure they are oriented properly and soldered to their pads. Reheat the solder joints with your iron and confirm continuity with your multimeter.

If it still only works in one orientation, sadly one of the six USB-C port pins has a bad connection to my PCB (damaged in shipping, most likely).

You can reflow these pins with your soldering iron, adding solder if needed. If you apply too much solder and the pins get bridged, you can use solder wick or a solder sucker to remove some.


### Did you accidentally lift up some of the original charging port's pads?

You can test with your multimeter that you have continuity from the USB-C port to the expected destination. You'll have to follow the traces or look up where they lead. You can often rewire directly to the destination if you've messed up the original charging port's pad.

### You heard a "click" or your console is no longer powering on

You might have just blown a fuse. Check F1 (or similar) for continuity and replace the part if necessary (replacement part list in the [Game Boy Discord](https://discord.gg/gameboy)). After searching for and fixing the short that caused the fuse to blow, of course!

### Still stuck?

If you're still stuck, the friendly folks in #modding on the [Game Boy Discord](https://discord.gg/gameboy) might be able to help you. Make sure you are patient and respectful - and clearly describe the problem and what you have tried to solve it so far.

I'm always available through Amazon/Tindie as well!