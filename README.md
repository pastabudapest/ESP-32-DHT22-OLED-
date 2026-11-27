

```markdown
## ESP-32 Temperature and Humidity Monitor
This project uses ESP32 with DHT22 sensor to measure temperature and humidity show on 0.96 OLED Screen
## Components
- ESP32
- DHT22 Temperature & Humidity Sensor
- 0.96 inch I2C OLED Display
- ESP32 Expansion Board

## How it works
The ESP32 reads data from the DHT22 sensor, then prints temperature and humidity values on the OLED screen.

## Libraries (PlatformIO)
- DHT sensor library
- Adafruit SSD1306
- Adafruit GFX Library

## Wiring
- DHT22 VCC → 3V
- DHT22 GND → GND
- DHT22 DATA → GPIO pin defined in code
- OLED VCC → 3V
- OLED GND → GND
- OLED SDA → GPIO21
- OLED SCL → GPIO22

## Source Code
```cpp
#include <Arduino.h>
#include <DHT.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>

#define DHTPIN 4
#define DHTTYPE DHT22
DHT dht(DHTPIN, DHTTYPE);

#define SCREEN_WIDTH 128
#define SCREEN_HEIGHT 64
Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire, -1);

void setup() {
  Serial.begin(115200);
  dht.begin();
  display.begin(SSD1306_SWITCHCAPVCC, 0x3C);
  display.clearDisplay();
  display.setTextSize(1);
  display.setTextColor(SSD1306_WHITE);
}

void loop() {
  float temp = dht.readTemperature();
  float hum = dht.readHumidity();

  display.clearDisplay();
  display.setCursor(0,0);
  display.print("Temp: ");
  display.print(temp);
  display.print(" C");
  display.setCursor(0,20);
  display.print("Hum: ");
  display.print(hum);
  display.print(" %");
  display.display();
  delay(2000);
}
## Project Demo Video

[Project functional demonstration video](https://youtube.com/shorts/-LNNiSevfIE?si=vu5QH4xUiGq77kCn)

