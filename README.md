# Temperature and Humidity Detector using Arduino and DHT11


This project is a Temperature and Humidity Monitoring System built using an Arduino Uno, DHT11 sensor, LCD display (16x2), and a breadboard. The system reads real-time temperature and humidity data from the DHT11 sensor and displays the values on the LCD screen. It can be used for applications like basic weather stations, smart homes, and environment monitoring.

# Components Used
Arduino Uno
DHT11 Temperature and Humidity Sensor
16x2 LCD Display
Breadboard
Jumper Wires
10kΩ Potentiometer (for LCD contrast control)
Resistor (optional, depending on setup)

# How It Works
The DHT11 sensor measures the surrounding temperature and humidity.
The Arduino reads the sensor data using a DHT library.
The collected data is displayed on the 16x2 LCD screen in real-time.
The system continuously updates the readings every few seconds.

# Features
Real-time temperature (°C) and humidity (%) display
Compact and easy-to-build setup
User-friendly and beginner-friendly Arduino project
Useful for basic environmental monitoring

# Circuit Diagram
(Given in images please download!)

# Arduino Libraries Used
DHT.h (for interfacing with the DHT11 sensor)
LiquidCrystal.h (for controlling the LCD)

# How to Run
Connect the components as per the circuit diagram.
Upload the provided Arduino sketch to the Arduino board.
Open the Serial Monitor to check sensor readings (optional).
Observe real-time temperature and humidity on the LCD screen.

# Future Improvements
Add data logging to an SD card
Send data wirelessly to a mobile app or web server using Wi-Fi (ESP8266) or Bluetooth modules.
Add alerts if temperature or humidity crosses a threshold.
