# Hardware Components

This document lists the main hardware used in the IoT-Based Smart Bin Management System.

| Component | Quantity | Purpose |
|---|---:|---|
| ESP8266 NodeMCU | 1 | Reads the sensor, calculates the fill level, and connects to Wi-Fi/Blynk |
| HC-SR04 ultrasonic sensor | 1 | Measures the distance from the sensor to the waste surface |
| Servo motor | 1 | Opens and closes the bin lid when commanded from Blynk |
| Jumper wires | As needed | Connect the components |
| Breadboard | 1 (optional) | Makes prototyping connections easier |
| Suitable power supply | As needed | Powers the NodeMCU, sensor, and servo as appropriate |
| Resistors: 1 kΩ and 2 kΩ | 1 each | Form the Echo voltage divider shown in the project wiring notes |

## Component Notes

### ESP8266 NodeMCU
The microcontroller reads the ultrasonic sensor, calculates the estimated bin fill percentage, and sends data to the Blynk IoT platform over Wi-Fi.

### HC-SR04 Ultrasonic Sensor
The sensor measures the distance between its position and the waste surface. The measured distance is used to estimate how full the bin is.

### Servo Motor
The servo controls the bin lid. The Blynk dashboard sends an open/close command to the ESP8266.

### Power and Voltage-Level Safety
- Check the exact NodeMCU board's VIN/5V input requirements.
- Do not feed the HC-SR04 5V Echo signal directly into an ESP8266 GPIO.
- Use a suitable voltage divider or logic-level shifter on Echo.
- A servo can draw more current than the NodeMCU board can safely provide. Use a suitable external supply if needed and connect the supply ground to NodeMCU GND.
