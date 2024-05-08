# HDT Testing Standard
## Introduction
This is an attempt at craeating an easy to follow procedure for standardised HDT testing of 3D printing polymers, taking inspiration from the ISO 75 methods.

As I haven't bought the ISO 75 standard publication, and considering the difficulties of actually making something easily reproducible by anyone with a 3D printer and a PID tuned oven, I have drafted the parameters of the test to make it simpler, losing some accuracy in the process.
This accuracy loss is not a problem as traditional ISO 75 tests require injection molded parts, as with FDM 3D printed parts too many parameters, some of which are not controllable, can influence the results.

Two load cases are suggested, to try and match the HDT/A and HDT/B values commonly found on 3D printer filaments technical datasheets.

<!-------------------------------------------------------------------------------------------------->
</br>

---

## Testing Methodology
### • Brief Description
A printed sample in the shape of a bridge is put inside a temperature controlled oven and slowly heat up. As soon as there is visible deformation the test is over and the last temperature value before the deformation is assumed to be the test result.

### • Printing Parameters
The test object shall be printed with the flat reference face laying downwards on the build plate.
The test object shall be scaled to account for material shrinkage during the printing process, so that the top reference surface is within the following dimensions:

| Dimension  | Value (mm) |
| ---------- | ---------- |
| Length     | 140 ±0.05 |
| Width      | 20 ±0.05  |
| Thickness  | 2 ±0.05   |

The object has to be printed with a 0.4mm/0.5mm nozzle, and the following settings have to be used in the slicer:

| Setting              | Value             |
| ----------           | ----------        |
| Line Width           | 0.8mm             |
| Layer Height         | 0.2mm             |
| N° of Perimeters     | 4                 |
| N° of Top Layers     | 0                 |
| N° of Bottom Layers  | 0                 |
| Infill %             | 100%              |
| Infill Type          | Rectilinear/Lines |
| Infill Angle         | 45°               |
| Print Speed          | 30mm/s            |

These settings have been chosen to get maximum possible strength to the part and maximize compatibility, and have been fixed to remove variability in the results.
The three parameters that have been left to be changed depending on the material are _Hotend Temperature_, _Chamber Temperature_ and _Cooling Fan Percentage_.
It is reccommended to note them and add them near the test results to make them valid and reproducible.

### • Test A - 1.8MPa (similar to HDT/A)
The bridge shall be loaded with 4 standard ISO 4032 or DIN 934 steel nuts (17.3g each), making sure they are stacked on top of each other securely and located in the middle of the bridge (marked with a line on the underside).

### • Test B - 0.45MPa (similar to HDT/B)
The bridge shall be loaded with 1 standard ISO 4032 or DIN 934 steel nuts (17.3g), making sure it is located in the middle of the bridge (marked with a line on the underside).

### • Temperature Rise
The oven shall be set with a ramp starting from 25°C rising 1°C/min, to make sure the parts can stabilize at the oven temperature and to give time for the parts to flex when they reach the softening point corresponding to the specified test.
The test stops when the first observable deformation happens.

### • Results
The results shall be distributed by specifying which load was used, and what were the _Hotend Temperature_, _Chamber Temperature_ and _Cooling Fan Percentage_ used for printing the sample.

<!-------------------------------------------------------------------------------------------------->
</br>

---

## Calculation of the stresses in each test case
In this section I'll add the calculations that led me to choose the size and loads to match the ISO 75 standard.

<!-------------------------------------------------------------------------------------------------->
</br>

---

## Comments
A lot of parameters were chosed seemingly arbitrarily, so I'll have to add a reason for why they were chosen.
