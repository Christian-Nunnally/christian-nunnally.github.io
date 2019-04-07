---
title: Led Display Tutorial
layout: default
---
# Led Display Tutorial
Coming soon! How to build a super cheap nXm ws8211 LED panel driven by [FadeCandy](https://github.com/scanlime/fadecandy) controllers

## Materials
- [FadeCandy - $25](https://www.amazon.com/Adafruit-FadeCandy-Dithering-USB-Controlled-NeoPixels/dp/B00JHJJF9W)
- [Strips of Ws8211 LEDs - ~$0.08/ea ($40 per FadeCandy)](https://www.ebay.com/itm/WS2812B-5050-RGB-LED-Strip-5M-150-300-Leds-144-30LED-M-Individual-Addressable-5V-/322058431958)
- [30A power supply - $19](https://www.amazon.com/gp/product/B01HJA3OUG/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1)
- [Heavy duty cardboard - $2.68](https://www.lowes.com/pd/Medium-Heavy-Duty-Cardboard-Moving-Box-Actual-18-in-x-16-in-x-18-in/50098524)
- 3/8" x 1/2" 'U' shaped extruded aluminum - $10
- (optional) Plexiglass - $10

Total cost for 4x 16x16 displays running on two FadeCandys = ~$200 = ~$0.20/pixel

*Note: You can dig around for cheaper Ws8211 LED's online which can bring down the cost further*

## Step #1: Determine the size
Depending on the size of the display you would like to make, you will need to do some calulations to figure out what size to cut things. Since this project is using a fadecandy as the driver, and each fadecady channel can drive up to 64 leds it helps to use these rules when deciding what size to make:
 * The width or height should be a power of 2
 * The width or height that is a power of two should be less than 64
 * It helps if you make the total number of LEDs divisible by 64, 128, 256, or 512
 Basically each fadecandy and 30A power supply will drive 512 LEDs, so try to make you project use some multiple of 512 leds. You can always scale horizontally with more fadecady/power supply combos.
 
For example, I decided to make a 16x16 display, which complies with all of the rules. I'm making 4 displays in total, 4(16)(16) = 1024, so I'll need two fadecandies and power supplies.
 
Once you've picked the size of your display in pixels, calculate how big to cut the cardboard as follows:

Width = 16mm + 17mm * #leds on side (this is for 60 leds/meter strips)
Height = 16mm + 17mm * #leds on side (this is for 60 leds/meter strips)

## Step #2: Cutting
Cut the cardboard sqaure out (size determined in step #1) that will be the backing of the led display. For my 16x16 display I cut out a 28cm by 28cm peice of heavy duty coard board. I chose cardboard for its unrivaled cost/weight/durability/workability compromises.

Next cut four peices of aluminum:
2x that are the same length as one side of your cardboard rectangle
2x that are 1" shorter than the length of the other size of your cardboard rectangle

## Step #3 (optional): Painting
I decided to paint everything black to help protect it agaisnt water damage and so it looks nice.

## Step #4: LEDs:
Cut your leds strips so that they are in strips whose length is equal to the side of your leds display that is a power of 2 (otherwise wiring will be a nightmare). In my case both sides were 16, so I cut 16x 16-long leds strips.

From 14m down on both sides of your cardboard that is not a power of 2, make marks every 17mm.

Lay the first led strip so that the top side lines up with the first marks and each side.

For the second strip, lay it along the next marks so that it is going in the opposite direction than the first.

Keep laying down each strip in this manner, alternating directions, until you've laid out all of the strips.

## Step #5: Soldering
Wire together the leds strips using little jumper cables. Make sure to stop every 64 leds since each bank of 64 will need to connect to a pin on the fadecandy board.

Wrap two layers of electrical tape over the solder connections, you want this to be well protected because the aluminum frame tends to pinch down on those connections.

## Step #6: Finishing up
Slide the aluminum frame onto the edge of the cardboard, this will be a tight fit around the wire ends, but it keeps everything from moving around once its in place, and the cardboard will smash slightly to allow the frame to slide on.

(Optional) Cut a peice of clear plastic the size of your display and glue it on to protect the LEDs.

## Programming the diplay
[Rendering shapes on the display](https://christian-nunnally.github.io/visual-drop-basic-tutorial.html)


