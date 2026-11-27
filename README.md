# ESP-32 Temperature and Humidity Monitor
This project uses ESP32 with DHT22 sensor to measure temperature and humidity show on 0.96 OLED Screen
# Components
- ESP32
- DHT22 Temperature & Humidity Sensor
- 0.96 inch I2C OLED Display
- ESP32 Expansion Board

# How it works
The ESP32 reads data from the DHT22 sensor, then prints temperature and humidity values on the OLED screen.

# Libraries (PlatformIO)
- DHT sensor library
- Adafruit SSD1306
- Adafruit GFX Library

# Wiring
- DHT22 VCC → 3V
- DHT22 GND → GND
- DHT22 DATA → GPIO pin defined in code
- OLED VCC → 3V
- OLED GND → GND
- OLED SDA → GPIO21
- OLED SCL → GPIO22
