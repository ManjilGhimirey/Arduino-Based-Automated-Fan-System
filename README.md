# Arduino-Based Automated Fan System 🌬️🔥

A temperature-controlled fan system using Arduino UNO, DHT11 sensor, and a relay module to automate fan operation based on real-time temperature.

## 🧰 Components Used
- Arduino UNO
- DHT11 Temperature Sensor
- Relay Module
- DC Fan
- Power Supply
- C/C++ (Arduino IDE)

## 📋 Features
- Real-time temperature monitoring
- Automatic fan activation based on threshold
- Energy-efficient control system
- Easy-to-build for home automation setups

## 🔌 Circuit Diagram
(Include Fritzing diagram or image here)

## 💻 Code Overview
The main script reads temperature from DHT11 and activates the fan if the temperature exceeds a set threshold (e.g., 30°C).

```cpp
#include <DHT.h>

#define DHTPIN 2
#define RELAYPIN 3
#define DHTTYPE DHT11

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  pinMode(RELAYPIN, OUTPUT);
  dht.begin();
}

void loop() {
  float temp = dht.readTemperature();
  if (temp > 30) {
    digitalWrite(RELAYPIN, HIGH);
  } else {
    digitalWrite(RELAYPIN, LOW);
  }
  delay(2000);
}
🛠️ Setup Instructions
Upload code to Arduino using Arduino IDE

Connect components as per diagram

Power on and observe fan control based on temperature

📌 Future Enhancements
Add an LCD display to show real-time temperature

Use IoT module (ESP8266) to monitor remotely

Integrate mobile app for manual override

