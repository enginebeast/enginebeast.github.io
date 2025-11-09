---
title: "Remote control app for Arduino RC car"
categories:
  - smallcar
comments: true
---

While working on my project, I realized that IR remote control wasn't suitable my project. The IR sensor doesn't work properly when obstacles block the signal. So, I decided to find another way to control my RC car.

First, I considered modifying the prototype RC car remote control. But, I canceled this decision, because I wasn't convinced that I was able to make arduino to receive radio waves of prototype remote control. 

Second, I considered using a smartphone remote control app with a Bluetooth module to control the RC car. Although the app maker’s UI for Arduino is limited, this isn’t a big problem. Initially, my goal in creating a remote control system was simply to check whether the RC car was working correctly, so I didn’t need detailed control. If I want more advanced control in the future, I can solve it at the Raspberry Pi level.

![Image](https://github.com/user-attachments/assets/c611d821-97a8-4f84-a014-2044b7cd1d0a)

First, I create the smartphone app UI to use MIT app inventor which is web site that helps you quikly build smartphone apps.

![Image](https://github.com/user-attachments/assets/7408de2c-3f4d-435d-bab1-b8202024b174)

But, there was a problem that UI is not user-friendly because, it's too close together.

I think it's because there is a function that arranges automatically. So, I inserted text labels filled with spaces between buttons, and it worked well.

<img width="786" height="649" alt="Image" src="https://github.com/user-attachments/assets/34bfa989-5466-409a-8e77-d7ed259125cd" />

Next, I programed the app using block editor of MIT app inventor. The above parts are used to connect the smartphone app to the Arduino via a Bluetooth module. Here is the [Youtube video](https://community.appinventor.mit.edu/t/app-inventor-arduino/18357) I refered to when making the above blocks. 

<img width="455" height="532" alt="image" src="https://github.com/user-attachments/assets/cf6c4896-afab-4964-8892-edeb2976f2ca" />

<img width="442" height="527" alt="image" src="https://github.com/user-attachments/assets/4b4f3156-44b3-4c18-afb6-72eef3e3e0e5" />

[Link](https://www.youtube.com/watch?v=xfmdanZ_Fgc&t=907s)
