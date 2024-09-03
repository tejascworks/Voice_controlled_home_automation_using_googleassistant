#define BLYNK_TEMPLATE_ID "Your Template ID"
#define BLYNK_DEVICE_NAME "Your Device Name"
#define BLYNK_AUTH_TOKEN "Your Auth Token"

#define BLYNK_PRINT Serial

#include <WiFi.h>
#include <WiFiClient.h>
#include <BlynkSimpleEsp32.h>

// WiFi credentials
char auth[] = BLYNK_AUTH_TOKEN;

char ssid[] = "your_wifi_ssid";
char pass[] = "your_wifi_password";

// Pin connected to the LED
const int ledPin = 2;

void setup()
{
  // Initialize serial port
  Serial.begin(115200);

  // Connect to WiFi network
  Blynk.begin(auth, ssid, pass);

  // Set the LED pin as an output
  pinMode(ledPin, OUTPUT);
}

void loop()
{
  // Run Blynk background tasks
  Blynk.run();
}

// Blynk virtual pin handler
BLYNK_WRITE(V0)
{
  int value = param.asInt(); 
  value ?  digitalWrite(ledPin, HIGH) :  digitalWrite(ledPin, LOW);
}
