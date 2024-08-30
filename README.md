# IoT-Based Smart Home Using Google Assistant

## Overview

The "IoT-Based Smart Home Using Google Assistant" project integrates various sensors and appliances with Google Assistant to enable voice-controlled smart home automation. This system uses an ESP8266 microcontroller to control relays, monitor environmental parameters, and publish sensor data to the Adafruit IO platform via MQTT. Control and monitor your home environment with ease using voice commands through Google Assistant.

## Features

- **Appliance Control**: Manage appliances via relays, enabling on/off control with voice commands.
- **Environmental Monitoring**: Track and publish temperature, humidity, CO2 levels, sound levels, and light intensity.
- **Google Assistant Integration**: Utilize Google Assistant for voice-activated control and monitoring.
- **Real-Time Data Publishing**: Send sensor data to Adafruit IO for real-time monitoring and control.

## Hardware Requirements

- **ESP8266 NodeMCU** or similar
- **4-Channel Relays** (for appliance control)
- **DHT11 Sensor** (for temperature and humidity)
- **Buzzer**
- **Analog Sensors** (Motion, CO2, Sound, Light)
- **Multiplexer** (for sensor switching)

## Software Requirements

- **Arduino IDE**
- **ESP8266 Board Package** for Arduino
- **Adafruit MQTT Library**
- **Adafruit DHT Library**
- **Google Assistant setup** for voice control

## Code Overview

The provided code handles WiFi and MQTT connections, subscribes to and publishes data from various sensors, and controls appliances. Key sections include:

### Libraries and Definitions

```cpp
#include <ESP8266WiFi.h>
#include "Adafruit_MQTT.h"
#include "Adafruit_MQTT_Client.h"
#include "DHT.h"

// Pin Definitions
#define Relay1            D6
#define Relay2            D2
#define Relay3            D1
#define Relay4            D5
#define DHTPIN            D7
#define buzzer            D0
#define S0                D3
#define S1                D4
#define analogpin         A0

// WiFi and MQTT Configuration
#define WLAN_SSID       "SSID_NAME"
#define WLAN_PASS       "PASSWORD"
#define AIO_SERVER      "io.adafruit.com"
#define AIO_SERVERPORT  1883
#define AIO_USERNAME    "AIO_USERNAME"
#define AIO_KEY         "AIO_KEY"
