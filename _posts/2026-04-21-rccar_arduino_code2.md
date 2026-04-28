---
title: "Arduino code for RC car ver.2"
categories:
  - car_project
---

You can find full code [here](https://github.com/enginebeast/ArduinoRCcar/blob/main/Control_car_ver2.ino). This page is just for recording what I learned from the project, so it doesn't include all the code.

In version 1 of the RC car code, the car cannot drive and steer at the same time. However, by adding the steering slider on the RC app, I was able to solve this problem. The following code receives data from the app and processes it.

```cpp
  String input;
  String drive;
  String steerStr;
  int steer;
  int commaIndex;
  
  if (BtSerial.available()){
    input = BtSerial.readStringUntil('\n');

  commaIndex = input.indexOf(",");
  drive = input.substring(0, commaIndex);
  steerStr = input.substring(commaIndex + 1);
  steer = steerStr.toInt();
```

First, Bluetooth must get driving data and steering angle data from RC app. But, Bluetooth module cannot get 2 data at once. So, I have to use a way get a String data. To get a String data, I must use ```readStringUntil('\n')``` instead of ```read()```.

Arduino don't know the end of the String data unless I specify the endpoint. (Computers are the same way.) This is why we use the endpoints in low-level languages, and the newline character is the most common type.
  
```cpp
  //Stop
  if (drive == "S"){
    digitalWrite(in1, HIGH);
    digitalWrite(in2, LOW);
    digitalWrite(in3, HIGH);
    digitalWrite(in4, LOW);
    analogWrite(speed_a , 0);
    analogWrite(speed_b , 0);
  }

  //Forward
  else if (drive == "F"){
    //More Left
    if (1 <= steer && steer < 256){
      digitalWrite(in1, LOW);
      digitalWrite(in2, HIGH);
      digitalWrite(in3, HIGH);
      digitalWrite(in4, LOW);
      analogWrite(speed_a, steer);
      analogWrite(speed_b, 255);
    }

    //Neutral and left
    else if (256 <= steer && steer <= 512){
      digitalWrite(in1, HIGH);
      digitalWrite(in2, LOW);
      digitalWrite(in3, HIGH);
      digitalWrite(in4, LOW);
      analogWrite(speed_a, steer - 257);
      analogWrite(speed_b, 255);
    }

    //Right
    else if (513 <= steer && steer <= 768){
      digitalWrite(in1, HIGH);
      digitalWrite(in2, LOW);
      digitalWrite(in3, HIGH);
      digitalWrite(in4, LOW);
      analogWrite(speed_a, 255);
      analogWrite(speed_b, 767 - steer);
    }

    //More Right
    else if (769 <= steer && steer <= 1023){
      digitalWrite(in1, HIGH);
      digitalWrite(in2, LOW);
      digitalWrite(in3, LOW);
      digitalWrite(in4, HIGH);
      analogWrite(speed_a, 255);
      analogWrite(speed_b, steer - 768);
    }
  }

  //Backward
  else if (drive == "B"){
    //More Left
    if (1 <= steer && steer <= 255){
      digitalWrite(in1, HIGH);
      digitalWrite(in2, LOW);
      digitalWrite(in3, LOW);
      digitalWrite(in4, HIGH);
      analogWrite(speed_a, steer);
      analogWrite(speed_b, 255);
    }

    //Neutral and left
    else if (256 <= steer && steer <= 512){
      digitalWrite(in1, LOW);
      digitalWrite(in2, HIGH);
      digitalWrite(in3, LOW);
      digitalWrite(in4, HIGH);
      analogWrite(speed_a, steer -257);
      analogWrite(speed_b, 255);
    }

    //Right
    else if (513 <= steer && steer <= 767){
      digitalWrite(in1, LOW);
      digitalWrite(in2, HIGH);
      digitalWrite(in3, LOW);
      digitalWrite(in4, HIGH);
      analogWrite(speed_a, 255);
      analogWrite(speed_b, 767 - steer);
    }

    //More right
    else if (769 <= steer & steer <= 1023){
      digitalWrite(in1, LOW);
      digitalWrite(in2, HIGH);
      digitalWrite(in3, HIGH);
      digitalWrite(in4, LOW);
      analogWrite(speed_a, 255);
      analogWrite(speed_b, steer - 768);
    }
  }
  }
}
```

After finding a slider UI, the way to steering became so simple. It's just had to slow down the wheel of side of the turn. Doing the math manually was far too tedious.