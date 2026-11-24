#Item
Quantity
Purpose
Arduino Uno
1
Microcontroller - ATmega328P
USB Cable
1
Power to the microcontroller
DHT11 temperature/humidity sensor
1
Measures temperature and humidity in the nearby space
Alphanumeric LCD, 16 x 2 
1
Displays the measurements of the temperature readings, average, and minimum and maximum values
10k  Potentiometer
1
Sets the value for the alarm
Green, yellow, red LEDS
3
Temperature status: normal, warm, alarm
220  resistors
3
Limits LED current
Piezo Buzzer
1
Alarm that emits sound to notify the user when the temperature is high
Push buttons
2
Display switches between Fahrenheit and Celsius
Breadboard & jumper wires
1
Wire connections between the microcontroller and the components


Ideas: 
Screens for temperature, humidity, over last few measurements
Main screen showing current temp and humidity, average over last few measurements, min/max
Use an array to store each reading
On startup, update the display quickly (at first reading) so display shows immediately
Buttons to change screens
Buzzer and/or LED for a temp over / under a certain threshold
If temp is hovering at threshold, the alarm might flicker on/off - Use separate on/off points (Ex: alarm on at 20 deg, alarm off at 29 deg)
A button press turns off the alarm
Change mode to celsius/farenheit
Error screen - If no readings available / readings stopped
Display Potentiometer reading converted to temp threshold
Log readings to serial
Maybe - Different button presses for actions (Ex: long press changes between celsius and fahrenheit)
