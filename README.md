#Sensor Test Code
#include <DHT.h>

#define DHTPIN 2     // Digital pin connected to the DHT11 sensor
#define DHTTYPE DHT11   // Define sensor type as DHT11

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(9600);
  Serial.println(F("DHT11 sensor test!"));

  dht.begin();
}

void loop() {
  // Wait 2 seconds between measurements (DHT11 is a slow sensor)
  delay(2000);

  // Read humidity
  float h = dht.readHumidity();
  // Read temperature as Celsius (default)
  float t = dht.readTemperature();
  // Read temperature as Fahrenheit (isFahrenheit = true)
  float f = dht.readTemperature(true);

  // Check if any reads failed and exit early (to try again)
  if (isnan(h) || isnan(t) || isnan(f)) {
    Serial.println(F("Failed to read from DHT sensor!"));
    return;
  }

  // Compute heat index in Fahrenheit and Celsius
  float hif = dht.computeHeatIndex(f, h);
  float hic = dht.computeHeatIndex(t, h, false);

  // Print results to Serial Monitor
  Serial.print(F("Humidity: "));
  Serial.print(h);
  Serial.print(F("%  |  "));
  Serial.print(F("Temperature: "));
  Serial.print(t);
  Serial.print(F("°C / "));
  Serial.print(f);
  Serial.print(F("°F  |  "));
  Serial.print(F("Heat Index: "));
  Serial.print(hic);
  Serial.print(F("°C / "));
  Serial.print(hif);
  Serial.println(F("°F"));
}

