UPDATE 20.01.2019:
Replaced Replay with Omron G5Q-1-EU DC12

UPDATE 19.12.2018:
- Tested today the relay with Arduino UNO on pin 2 which is configured with PULL UP resistor. The circuit worked very good and the capacitor successfully reported only LOW as long as the AC light is ON, and HIGH as long as the AC is OFF. 

TODO: Test the circuit with long wiring more than 25 meters and put the capacitor near the controller itself and monitor the performance.
The above TODO has been verified successfully 

# Relay_zcd
Relay circuit to control a relay and detect the status of the AC switch using SFH620A optocoupler. 
The idea is to be used in a Smart House to be able to connect the relay with a 3 way switch. It is important to detect the light state so that the application can decide whether to turn off or on the relay. 
The optocoupler is normally pulled to HIGH and goes LOW when the AC is rising which turns on the LED in the optocoupler. When the LED is ON the transistor in the SFH620A will connect the output Signal to GND.
Normally the pin wil be low for ~9ms and high for ~1ms. To avoid this pulsing the idea is to add a capacitor with value 0.1uF to delay the rising of the pin to HIGH when the AC is at zero crossing detection.
