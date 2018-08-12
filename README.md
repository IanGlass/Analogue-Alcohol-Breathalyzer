# Analogue-Alcohol-Breathalyzer
The aim of this project was to build a alcohol breathalyzer using only analogue components. The breathalyzer has three indicators of alcohol concentration and can be calibrated using three potentiometers.

## Voltage Regulator
The circuit can handle any input voltage between 6 and 18 V, using a LM7805 voltage regulator to achieve a steady 5 V feed to the circuit.
<p align="center">
<img src="https://github.com/IanGlass/Analogue-Alcohol-Breathalyzer/blob/master/Voltage-Regulator.JPG" width="1000">
</p>

## Sensor Bridge
The alcohol breathalyzer works on the MQ-3 gas sensor, which is temporarily oxidized in the presence of alcohol, changing it's resistance. Resistance can be transduced using a voltage divider, in this case a load RL of 22 k ohm is used for the nominal 14 k ohm sensor.
![Sensor equation](https://latex.codecogs.com/gif.latex?V_%7Bsig%7D%3D%5Cfrac%7BV_%7Bcc%7DR_%7BL%7D%7D%7BR_%7BL%7D&plus;R_%7Bs%7D%7D)
<p align="center">
<img src="https://github.com/IanGlass/Analogue-Alcohol-Breathalyzer/blob/master/Sensor.JPG" width="1000">
</p>
However, the heating effect of running current through a resistive element means that the breathalyzer needs a warm-up period.

## Timing Circuit
The timing circuit provides an LED to indicate when the breathalyzer has warmed up. The circuit works by using a comparator with an RC input and a voltage divider input. Once the RC circuit charges to a greater voltage than the divider, the comparator turns on. In other words, the comparator switches when the RC circuit (expressed below) exceeds the reference voltage on V- of 3.24 V.
![Charge up equation](https://latex.codecogs.com/gif.latex?v_%7B&plus;%7D%20%3D%20v_%7Bcmax%7D.e%5E%7Bt/rc%7D)
<p align="center">
<img src="https://github.com/IanGlass/Analogue-Alcohol-Breathalyzer/blob/master/Timing-Circuit.JPG" width="1000">
</p>

## Comparator Circuit
The breathalyzer has three indicators: low alcohol, medium alcohol and high alcohol concentrations indicated with three separate LEDs (green, yellow and red). LEDs are turned on using comparators which switch when Vsig exceeds the reference voltage provided below.
<p align="center">
<img src="https://github.com/IanGlass/Analogue-Alcohol-Breathalyzer/blob/master/Voltage-Divider.JPG" width="1000">
</p>
LEDs are only lit up while a alcohol source is supplied, as soon as the user stops blowing, the LEDs switch off. This was mitigated using feedback latching. The comparator self-latches once it has been triggered and must be reset before taking a new reading. The diode prevents the feedback latch from triggering other comparators on the same Vsig line. Reseting is achieved by placing an active low button on the OpVCC line.
<p align="center">
<img src="https://github.com/IanGlass/Analogue-Alcohol-Breathalyzer/blob/master/Low-Comparator.JPG" width="1000">
</p>
<p align="center">
<img src="https://github.com/IanGlass/Analogue-Alcohol-Breathalyzer/blob/master/Medium-Comparator.JPG" width="1000">
</p>
<p align="center">
<img src="https://github.com/IanGlass/Analogue-Alcohol-Breathalyzer/blob/master/High-Comparator.JPG" width="1000">
</p>
