
# Features (NEMA 17HS4401 Bipolar Stepper Motor)

##   Mechanic Features

![[Pasted image 20230901111746.png| 550]]

## Electrical Features

- Motor Type: Bipolar Stepper
- Step Angle: 1.8 deg.
- Holding Torque: 40N.cm (56oz.in)
- Rated Current/phase: *1.7A*
- Phase Resistance: 1.5Ohm±10%
- Insulation Resistance: 100MΩ¸ Min, 500VDC
- Insulation Strength: 500VAC for one minute
# A4988 

## Vref  Modification

>Function 

```
Vref = Irated * Res * 8
/ * It’s strongly recommended to reduce the amount of current to the motor by at least 10% */
```

|Irated(A) | Res(Ω) | Vref(V) |
|:---:| :---:| :---:|
|    1.7  |  0.1   |    1.224  |

## Measure Methodology:

To adjust VREF , follow these steps:
1. Without turning the power on, plug the driver into the controller board of choice
Make sure to mount it correctly. Note that, for the Ramps 1.4 board, it must beattached to the Arduino Mega, too.
2. Power up the board  via VDD (+5V) and GND, not via USB.
3. Set the multimeter to DC voltage and to the proper scale (around 2 V).4. Place the black probe on the controller board's GND as shown in the image.5. Carefully place the red probe on the driver potentiometer to measure VREF as shown in the image special attention to the red probe - even touching other components could potentially short the driver or the controller board.
4. Power off the board to use a screw driver to adjust the value (Usually Clock-wise for increment)
![[Screenshot 2023-09-01 115729.png|550]]


# Pin-Mode #A4988
![[Screenshot 2023-09-01 105205.png|550]] 
from www.dronebotworkshop.com 


