# Battery Management System Setup Guide

## Overview
This guide will help you set up the Battery Management System (BMS) using an Arduino or compatible microcontroller, along with the necessary sensors for monitoring battery performance.

## Hardware Requirements
- **Arduino Board** (e.g., Arduino Uno, Mega, ESP8266, or any compatible board)
- **Voltage Sensor Module**
- **Current Sensor Module**
- **Temperature Sensor** (e.g., LM35, DHT11, or DS18B20)
- **Relay Module** (for controlling charging/discharging)
- **Breadboard and Jumper Wires**
- **Battery Pack** (Li-ion or Li-Po battery for testing)

## Wiring Diagram
Below is a simple wiring diagram to connect the sensors and relay to your Arduino. Ensure to follow the pin connections as described below.

```plaintext
         +----------------+
         |   Arduino      |
         |                |
         |   A0  ----->   |----> Voltage Sensor
         |   A1  ----->   |----> Current Sensor
         |   A2  ----->   |----> Temperature Sensor
         |   D2  ----->   |----> Relay Module (Control Pin)
         |                |
         +----------------+
```
## Pin Connections

### Voltage Sensor:
- **VCC**: Connect to Arduino 5V.
- **GND**: Connect to Arduino GND.
- **Output Pin**: Connect to Arduino A0.

### Current Sensor:
- **VCC**: Connect to Arduino 5V.
- **GND**: Connect to Arduino GND.
- **Output Pin**: Connect to Arduino A1.

### Temperature Sensor:

#### LM35:
- **VCC**: Connect to Arduino 5V.
- **GND**: Connect to Arduino GND.
- **Output Pin**: Connect to Arduino A2.

#### DHT11:
- **VCC**: Connect to Arduino 5V.
- **GND**: Connect to Arduino GND.
- **Data Pin**: Connect to Arduino A2 (add a pull-up resistor if required).

### Relay Module:
- **VCC**: Connect to Arduino 5V.
- **GND**: Connect to Arduino GND.
- **Control Pin (IN)**: Connect to Arduino D2.

## Software Requirements
1. **Arduino IDE**: Download and install the Arduino IDE from the [official website](https://www.arduino.cc/en/software).
2. **Required Libraries**:
   - **DHT Sensor Library** (if using DHT11).
   - **OneWire** and **DallasTemperature** libraries (if using DS18B20).

## Installation Steps

### Step 1: Install Arduino IDE
1. Visit the [Arduino IDE download page](https://www.arduino.cc/en/software).
2. Select the installer for your operating system and download it.
3. Follow the installation instructions provided on the website.

### Step 2: Install Required Libraries
1. Open the Arduino IDE.
2. Go to **Sketch > Include Library > Manage Libraries**.
3. In the Library Manager, search for and install the following:
   - **DHT sensor library** for DHT11.
   - **DallasTemperature library** for DS18B20 (if applicable).

### Step 3: Upload the Code
1. Open the `bms.ino` file in the Arduino IDE (make sure the code is ready as described in the previous sections).
2. Connect your Arduino board to your computer using a USB cable.
3. Select the correct board and port:
   - **Tools > Board > Select your board type** (e.g., Arduino Uno).
   - **Tools > Port > Select the COM port of your Arduino**.
4. Click the **Upload** button (right arrow icon) to upload the code to your Arduino.

### Step 4: Power the System
1. After successfully uploading the code, disconnect the Arduino from the USB and power it using an appropriate battery pack.
2. Ensure all connections are secure and that the battery is connected properly.

## Testing the System
1. Open the Serial Monitor in the Arduino IDE by pressing `Ctrl + Shift + M` or by navigating to **Tools > Serial Monitor**.
2. Set the baud rate to **9600** to see the real-time readings for voltage, current, and temperature.
3. Monitor the output for any alerts related to under-voltage or over-temperature conditions.

## Important Notes
- **Safety**: Always handle batteries with care to prevent short circuits or accidents. Follow proper safety guidelines.
- **Calibration**: Depending on your sensor specifications, you may need to calibrate the sensors for accurate readings. Adjust the calibration factors in your code if necessary.
- **Relay Control**: Test the relay operation with a lower voltage load initially to ensure it functions correctly before connecting to the battery.

