# HDT Testing Standard
## Introduction
This is an attempt at creating an easy to follow procedure for standardised HDT testing of 3D printing polymers, taking inspiration from the ISO 75 methods.

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
The test bridge shall be printed with the flat rectangular reference face laying downwards on the build plate. <br />
The test pillar shall be printed with the flat rectangular reference face laying downwards on the build plate. <br />
The test parts shall be scaled to account for material shrinkage during the printing process, so that the top reference surface of the bridge is within the following dimensions:

| Dimension  | Value (mm) |
| :--------- | :--------: |
| Length     | 140 ±0.2   |
| Width      | 20 ±0.2    |
| Thickness  | 2 ±0.1     |


The objects shall be printed with a 0.4mm/0.5mm nozzle, and the following settings have to be used in the slicer:

| Setting              | Value               |
| :----------          | :----------:        |
| Line Width           | 0.65mm              |
| Layer Height         | 0.2mm               |
| N° of Perimeters     | 4                   |
| N° of Top Layers     | 0                   |
| N° of Bottom Layers  | 0                   |
| Infill %             | 100%                |
| Infill Type          | Aligned Rectilinear |
| Infill Angle         | 0°                  |
| Print Speed          | 30mm/s              |
| Extrusion Multiplier | 1.05                |

These settings have been chosen to get maximum possible strength to the part and maximize compatibility, and have been fixed to remove variability in the results. <br />
The three parameters that have been left to be changed depending on the material are _Hotend Temperature_, _Chamber Temperature_ and _Cooling Fan Percentage_. <br />
It is reccommended to note them and add them near the test results to make them valid and reproducible. <br />

Before printing it has to be verified that when requesting 100mm of extrusion, 100mm of filament are extruded. If not an e-steps calibration must be performed. <br />
The filament diameter must be measured with a caliper and set correctly in the slicer.

### • Test A - 1.8MPa (similar to HDT/A)
The test bridge shall be loaded with 4 standard ISO 4032 or DIN 934 steel nuts (17.3g each), making sure they are stacked on top of each other securely and located in the middle of the bridge (marked with a line on the underside).

### • Test B - 0.45MPa (similar to HDT/B)
The test bridge shall be loaded with 1 standard ISO 4032 or DIN 934 steel nuts (17.3g), making sure it is located in the middle of the bridge (marked with a line on the underside).

### • Pillar Positioning
The test pillar shall be positioned under the middle of the bridge, such as the thin part at the top runs perpendicular to the span of the test bridge.

<picture>
  <img alt="Test setup image" src="/HDT_Setup.png">
</picture>

### • Shielding
The test objects shall be shielded with some aluminium foil from radiant sources of heat of the oven, by making a foil barrier between the emitting source and the object.

### • Temperature Rise
The oven shall be set with a ramp starting from 25°C rising 1°C/min, to make sure the parts can stabilize at the oven temperature and to give time for the parts to flex when they reach the softening point corresponding to the specified test. <br />
The test stops when the middle of the test bridge touches the top of the pillar.

### • Results
The results shall be distributed by specifying which load was used, and what were the _Hotend Temperature_, _Chamber Temperature_ and _Cooling Fan Percentage_ used for printing the sample.
The temperature chosen as the test result is 1° less than the temperature recorded at the end of the test.

### • Automation
To automate the test and to get more accurate results, it is recommended to attach copper/aluminium tape on the bottom of the bridge and on the top of the pillar, and connect them to two pins on an Arduino or a Raspberry Pi, so that when the objects touch and the test end, the circuit is closed and a signal is sent to the microcontroller.

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
I'm currently thinking about a more repeatable method to determine the exact temperature a specific deformation occurs, to make the test less dependant on human decisions

You can also download the model on Printables for free to support me:

https://www.printables.com/it/model/873223-heat-deflection-temperature-hdt-tester
