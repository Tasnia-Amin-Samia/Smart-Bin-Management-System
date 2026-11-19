# Circuit Connections

This document describes the connections used by `SmartBinManagement.ino`.

## HC-SR04 Ultrasonic Sensor

| HC-SR04 pin | Connection |
|---|---|
| VCC | Suitable 5V supply / NodeMCU VIN, after checking the board |
| GND | NodeMCU GND |
| TRIG | NodeMCU D5 |
| ECHO | NodeMCU D6 through a voltage divider |

### Echo Voltage Divider

The HC-SR04 Echo output may be 5V, while ESP8266 GPIO pins are not 5V tolerant.

Use the divider below:

```text
HC-SR04 ECHO ---- 1 kΩ ----+---- NodeMCU D6 (ECHO)
                           |
                          2 kΩ
                           |
                          GND
```

Do **not** connect Echo directly to D6.

## Servo Motor

| Servo wire | Connection |
|---|---|
| Signal (usually yellow/orange) | NodeMCU D7 |
| VCC (usually red) | Suitable servo power supply |
| GND (usually brown/black) | Supply GND and common NodeMCU GND |

Check the servo's voltage and current requirements. Do not assume the NodeMCU 3.3V pin can power the servo.

## Pin Summary

| Function | NodeMCU pin |
|---|---|
| Ultrasonic TRIG | D5 |
| Ultrasonic ECHO (after voltage divider) | D6 |
| Servo signal | D7 |

## Before Powering On

1. Check every connection against your actual board labels.
2. Confirm that the Echo voltage divider is connected correctly.
3. Make sure all required grounds are common.
4. Use a suitable power supply for the servo.
5. Keep the sensor stable and point it toward the inside of the bin.
