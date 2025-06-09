#include <Servo.h>

const int gasSensorPin = A0;      // MQ2 analog output
const int buzzerPin = 8;          // Buzzer
const int servoPin = 9;           // Servo moto

const int gasThreshold = 300;

Servo gasValve;

void setup() {
  pinMode(gasSensorPin, INPUT);
  pinMode(buzzerPin, OUTPUT);

  gasValve.attach(servoPin);
  gasValve.write(0); 

  Serial.begin(9600);

}

void loop() {
  int gasLevel = analogRead(gasSensorPin);
  Serial.print("Gas Level: ");
  Serial.println(gasLevel);

  if (gasLevel > gasThreshold) {
    digitalWrite(buzzerPin, HIGH);   
    gasValve.write(90);              
  } else {
    digitalWrite(buzzerPin, LOW);   
    gasValve.write(0);               
  }

  delay(1000);

}






