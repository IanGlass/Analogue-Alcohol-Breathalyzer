# Analogue-Alcohol-Breathalyzer

The alcohol breathalyzer works on the MQ-3 gas sensors, which is temporarily oxidized in the presence of alcohol, changing it's resistance. Three comparator are used to light up three coloured LEDs, indicative of alcohol concentration.

The MQ-3 sensor requires a minimum warm-up time to operate accurately and as such a timing circuit has been included with a 'status ready' LED. 

A peak-wave detector can be included to increase the time a user has to read the LED when alcohol is removed from the sensor (see report).

Input voltage: 6.5 V

Noise: 20u V p-p

SNR: 330 dB

Warm-up time: ~2 min

<img src="https://github.com/IanGlass/Analogue-Alcohol-Breathalyzer/blob/master/Breathalyzer-Schematic.JPG" width="1000">
<img src="https://github.com/IanGlass/Analogue-Alcohol-Breathalyzer/blob/master/Comparator.png" width="700">