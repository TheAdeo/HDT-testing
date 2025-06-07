# HDT Testing Standard v3.0
## Introduction
This is an attempt at creating an easy to follow procedure for an easy and DIY standardised HDT testing of 3D printing polymers, taking inspiration from the ISO 75 methods.

Considering the difficulties of actually making something easily reproducible by anyone with a 3D printer and a PID tuned oven, I have drafted the parameters of the test to make it simpler than the ISO 75 standard, losing some accuracy in the process and making the results of the two not directly comparable (but still close).
This accuracy loss is not a problem as traditional ISO 75 tests require injection molded samples, as with FDM 3D printed samples too many parameters, some of which are not controllable, can influence the results.

Two load cases are suggested, to try and match the HDT/A and HDT/B values commonly found on 3D printer filaments technical datasheets.

A big difference compared to the ISO 75 test is that the temperature ramp is four times as slow, to allow time for the sample to deform and get a number that's more true to real life compared to a faster test that always overestimates the result.

<!-------------------------------------------------------------------------------------------------->
</br>

---

## Testing Methodology
### • Brief Description
A printed sample in the shape of a bridge is put inside a temperature controlled oven and slowly heat up. As soon as the deformation is enough for the bridge to touch a fixed height gauge the test is over and the last temperature value at the fail instant is assumed to be the test result.

### • Printing Parameters
The test sample shall be printed with the flat rectangular reference face laying downwards on the build plate. <br />
The test sample shall be scaled to account for material shrinkage during the printing process, so that the top reference surface of the bridge is within the following dimensions:

| Dimension  | Value (mm) |
| :--------- | :--------: |
| Length     | 140 ±0.2   |
| Width      | 20 ±0.2    |
| Thickness  | 2 ±0.1     |


The test object shall be printed with a 0.4mm/0.5mm nozzle, and the following settings have to be used in the slicer:

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

Both the Classic and Arachne slicing engines are allowed. <br />

The height gauge can be printed with any slicer parameters, as long as it's made out of the same material as the test sample or out of a material with better thermal properties.

These settings have been chosen to get maximum possible strength to the sample and maximize compatibility, and have been fixed to remove variability in the results. <br />
The three parameters that have been left to be changed depending on the material are _Hotend Temperature_, _Chamber Temperature_ and _Cooling Fan Percentage_. <br />
It is reccommended to note them and add them near the test results to make them valid and reproducible. <br />

Before printing it has to be verified that when requesting 100mm of extrusion, 100mm of filament are extruded. If not an e-steps calibration must be performed. <br />
The filament diameter must be measured with a caliper and set correctly in the slicer.

### • Test A - 1.8MPa (similar to HDT/A)
The test sample shall be loaded with 4 standard ISO 4032 or DIN 934 M12 steel nuts (17.3g each), making sure they are stacked on top of each other securely and located in the middle of the bridge (marked with lines on the underside).

### • Test B - 0.45MPa (similar to HDT/B)
The test sample shall be loaded with 1 standard ISO 4032 or DIN 934 M12 steel nuts (17.3g), making sure it is located in the middle of the bridge (marked with lines on the underside).

### • Height Gauge Setup
After loading the bridge with the nuts, the M3x8 screw on the height gauge shall to be fixed at 1mm below the bottom surface of the bridge by tightening the M3 nut (that acts as a jam nut) against the M3 threaded insert. The 1mm could be measured with calipers subtracting the height of the gauge from the height of the loaded bridge, or by using a 1±0.1mm shim.
Different setups are allowed, as long as they can be tuned so that the fail criteria is 1mm of additional deformation after the test start.

<picture>
  <img alt="Test setup image" src="/HDT_Setup.png">
</picture>

### • Shielding
The test objects should be shielded with some aluminium foil from radiant sources of heat of the oven, by making a foil barrier between the emitting source and the object.

### • Temperature Rise
The oven shall be set with a ramp starting from 25°C rising 0.5°C/min, to make sure the sample can stabilize at the oven temperature and to give time for the sample to flex when it reaches the softening point corresponding to the specified test. <br />
The test stops when the sample flexes enough to touch the height gauge, or when 1mm of additional deformation is measured.

### • Results
The results shall be distributed by specifying which load was used, the test version (currently v3.0), and what were the _Hotend Temperature_, _Chamber Temperature_ and _Cooling Fan Percentage_ used for printing the sample.
The temperature chosen as the test result is the last temperature recorded at the end of the test, rounded to the nearest integer.
Multiple samples are highly suggested, in that case the result is the arithmetic average of the individual results, rounded to the nearest integer.

<!-------------------------------------------------------------------------------------------------->
</br>

---

## Calculation of the stresses in each test case
In this section I'll add the calculations that led me to choose the size and loads to match the ISO 75 standard.

<!-------------------------------------------------------------------------------------------------->
</br>

---

## Comments
I have to add the calculations that led me to these parameters.
I have to explain a way to automate the test, to remove the human factor entirely.
You can also download the model on Printables for free to support me (not updated to v3.0 yet, still v2.0 files):

https://www.printables.com/model/1055576-heat-deflection-temperature-hdt-tester-v2
