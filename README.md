# TinkerCAD-WaterSensingCode


// code from here down

const int waterSensorPin = A0;  
const int ledPin1 = 13; 
const int ledPin2 = 12;  
const int ledPin3 = 11;

void setup() {
  pinMode(ledPin1, OUTPUT);
  pinMode(ledPin2, OUTPUT);
  pinMode(ledPin3, OUTPUT); 
}

void loop() {
  int sensorValue = analogRead(waterSensorPin);

  if(sensorValue < 350) {
    digitalWrite(ledPin1, HIGH);
    digitalWrite(ledPin2, LOW); 
    digitalWrite(ledPin3, LOW);
  }
  else if(sensorValue < 450) {
    digitalWrite(ledPin1, LOW); 
    digitalWrite(ledPin2, HIGH);
    digitalWrite(ledPin3, LOW);
  }
  else {
    digitalWrite(ledPin1, LOW);
    digitalWrite(ledPin2, LOW);
    digitalWrite(ledPin3, HIGH);
  }

  delay(100);
}
