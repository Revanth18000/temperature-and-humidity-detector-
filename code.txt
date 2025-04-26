#include <LiquidCrystal.h>

#include <DHT.h>

// Define LCD pins (RS, E, D4, D5, D6, D7)
LiquidCrystal lcd(7, 6, 5, 4, 3, 8);

// Define DHT Sensor
#define DHTPIN 2       // Pin connected to DHT sensor
#define DHTTYPE DHT11  // Change to DHT22 if using DHT22

DHT dht(DHTPIN, DHTTYPE);

void setup() {
    Serial.begin(9600);
    dht.begin();
    
    // Initialize LCD
    lcd.begin(16, 2);
    lcd.setCursor(0, 0);
    lcd.print("Temp Detector");
    delay(2000);
    lcd.clear();
}

void loop() {
    float temp = dht.readTemperature(); // Get temperature in Celsius
    float hum = dht.readHumidity();     // Get humidity

    if (isnan(temp) || isnan(hum)) {
        Serial.println("Failed to read from DHT sensor!");
        lcd.setCursor(0, 0);
        lcd.print("Sensor Error!");
        return;
    }

    // Print to Serial Monitor
    Serial.print("Temp: ");
    Serial.print(temp);
    Serial.println(" °C");
    Serial.print("Humidity: ");
    Serial.print(hum);
    Serial.println(" %");

    // Display on LCD
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print("Temp: ");
    lcd.print(temp);
    lcd.print(" C");

    lcd.setCursor(0, 1);
    lcd.print("Humidity: ");
    lcd.print(hum);
    lcd.print(" %");

    delay(2000); // Refresh every 2 seconds
}

