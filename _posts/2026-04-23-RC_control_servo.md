---
title: "Controlling a servo motor with remote control"
categories:
  - car_project
---

```cpp
#include <Servo.h>
#include <SoftwareSerial.h>

Servo steer;
int Rx = 6; //Receiving pin
int Tx = 7; //Transmitting 
int Servo = 8;

SoftwareSerial BtSerial(Rx,Tx);

unsigned long lastTime = 0;
int currentSteer = 1500;

void setup() {
  Serial.begin(9600);
  BtSerial.begin(9600);

  steer.attach(Servo, 500, 2500);
}

void loop() {
  if (BtSerial.available()) {
    switch(BtSerial.read()){
      //Center
      case 3:
      steer.writeMicroseconds(1500);
      break;

      //Left
      case 4:
      steer.writeMicroseconds(2000);
      break;
      
      //Right
      case 5:
      steer.writeMicroseconds(1000);
    }
  }
}
```