# CanSat 2018-2019

This repository has the code we developed for participating in the International Cansat competiton at Texas, USA ([Visit our page](https://sites.google.com/view/launchpadsjce/home)). 
The hardware that we designed had the follwing modules used:

    1. BMP180 (for measuring pressure and temperature)
    2. Ublox NEO-M8N GPS (for measuring GPS position)
    3. ADXL345 (for measuring pitch and roll)
    4. AH49E hall effect sensor (for measuring blade spin rate)
    5. DS3231 (for mission time)
    6. Resistors (for measuring battery voltage)
    7. Xbee (for communication with ground station)
    
The code was devloped in Arduino IDE and have the following libraries used,

    1. SoftwareSerial.h
    2. DS3231.h
    3. Wire.h
    4. XBee.h
    6. AltSoftSerial.h
    7. TinyGPS++.h
    8. Adafruit_BMP085.h
    9. String.h
    
The software is able to sample every sensor at **1Hz rate**(1 sample per second) and relay it back to ground station. So at the gorund station,
we get 1 sample each second(through Xbee). 

### The data frame format
The sofware samples every sensor and make the data to a frame that we have designed. The follwing will be the format.
TEAM ID,MISSION TIME,PACKET COUNT,ALTITUDE,PRESSURE,TEMP,VOLTAGE,GPS TIME,GPS LATITUDE,GPS LONGITUDE,GPS ALTITUDE,GPS SATS,PITCH,ROLL,BLADE SPIN RATE,SOFTWARE STATE
