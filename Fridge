// Constants
const int tempPin = A0;  // LM35 output pin connected to Arduino A0
const int relayPin = 8;  // Relay control pin connected to Arduino Digital Pin 8

// Temperature thresholds
const float tempThresholdHigh = 4.0; // Temperature to turn cooling ON (in Celsius)
const float tempThresholdLow = 2.0;  // Temperature to turn cooling OFF (in Celsius)

void setup() {
  pinMode(relayPin, OUTPUT);
  digitalWrite(relayPin, LOW);  // Start with the cooling system off
  Serial.begin(9600);
}

void loop() {
  int sensorValue = analogRead(tempPin);
  float temperature = sensorValue * (5.0 / 1023.0) * 100.0; // Convert to Celsius
  Serial.print("Temperature: ");
  Serial.print(temperature);
  Serial.println(" C");
  
  if (temperature > tempThresholdHigh) {
    digitalWrite(relayPin, HIGH); // Turn the cooling system ON
  } else if (temperature < tempThresholdLow) {
    digitalWrite(relayPin, LOW);  // Turn the cooling system OFF
  }
  
  delay(1000); // Wait for 1 second before the next reading
}
