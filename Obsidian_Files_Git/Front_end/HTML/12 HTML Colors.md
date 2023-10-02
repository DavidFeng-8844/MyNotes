
## RGB & RGBA Color Values 

rgb(_red,_ _green_, _blue_)

Each parameter (red, green, and blue) defines the intensity of the color with a value between 0 and 255.

This means that there are 256 x 256 x 256 = 16777216 possible colors!

## RGBA Color Values

RGBA color values are an extension of RGB color values with an Alpha channel - which specifies the opacity for a color.

An RGBA color value is specified with:

rgba(_red,_ _green_, _blue, alpha_)

The alpha parameter is a number between 0.0 (fully transparent) and 1.0 (not transparent at all):

Experiment by mixing the RGBA values below:


## HEX Color

In HTML, a color can be specified using a hexadecimal value in the form:

``` html
#_rrggbb_
```

Where rr (red), gg (green) and bb (blue) are hexadecimal values between 00 and ff (same as decimal 0-255).

For example, # ff0000 is displayed as red, because red is set to its highest value (ff), and the other two (green and blue) are set to 00.

Another example, # 00ff00 is displayed as green, because green is set to its highest value (ff), and the other two (red and blue) are set to 00.

## Shades of Gray



## HSL Color Values

In HTML, a color can be specified using hue, saturation, and lightness (HSL) in the form:

hsl(_hue_, _saturation_, _lightness_)

Hue is a degree on the color wheel from 0 to 360. 0 is red, 120 is green, and 240 is blue.