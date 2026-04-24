---
title: "Arduino code for RC car ver.2"
categories:
  - car_project
comments: true
---

You can see all code here [link].

From version 1 of RC car code, it cannot drive and steer at once. But, by adding the slider for steering, I can solve this problem. This is the code to get the data from remote control and computing it.

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

First, Bluetooth must get driving and steering angle data from RC app. But, Bluetooth module cannot get 2 data at once. So, I have to use a way get a String data. To get a String data, I must use readStringUntil('\n') instead of read().

What 

Arduino don't know the end of the String data.
  
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
    //Left
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

    //Right
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
    //Left
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

    //Right
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