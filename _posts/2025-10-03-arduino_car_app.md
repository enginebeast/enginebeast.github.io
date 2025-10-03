---
title: "Controlling a servo motor through laptop connection"
categories:
  - smallcar
comments: true
---

While working on my project, I realized that IR remote control wasn't suitable my project. The IR sensor doesn't work properly when obstacles block the signal. So, I decided to find another way to control my RC car.

First, I considered modifying the prototype RC car remote control. But, I canceled this decision, because I wasn't convinced that I was able to make arduino to receive radio waves of prototype remote control. 

Second, I considered using a smartphone remote control app with a Bluetooth module to control the RC car. Although the app maker’s UI for Arduino is limited, this isn’t a big problem. Initially, my goal in creating a remote control system was simply to check whether the RC car was working correctly, so I didn’t need detailed control. If I want more advanced control in the future, I can solve it at the Raspberry Pi level.

<img width="384" height="629" alt="image" src="https://github.com/user-attachments/assets/14d0e229-30c2-4883-babd-6e7872e46f1a" />

First, I create the smartphone app UI to use MIT app inventor which is web site that helps you quikly build smartphone apps.

![Screenshot_20250815_213215](https://github.com/user-attachments/assets/a39fa935-1650-445a-9d3c-2acbeab0afa0)

But, there was a problem that UI is not user-friendly because, it's too close together.

![Screenshot_20250815_213259](https://github.com/user-attachments/assets/f1646dca-83fa-407d-afa2-dd2056af3af9)

I think it's because there is a function that arranges automatically. So, I inserted text labels filled with spaces between buttons, and it worked well.

<img width="789" height="683" alt="image" src="https://github.com/user-attachments/assets/1ea112cb-42da-4197-a360-01c480a42b76" />

Next, I programed the app using block editor of MIT app inventor. The above parts are used to connect the smartphone app to the Arduino via a Bluetooth module. Here is the [Youtube video](https://community.appinventor.mit.edu/t/app-inventor-arduino/18357) I refered to when making the above blocks. 

<img width="455" height="532" alt="image" src="https://github.com/user-attachments/assets/743d38fa-090a-4fd4-86bf-cd0f749f3c39" />  
  
<img width="442" height="527" alt="image" src="https://github.com/user-attachments/assets/744af61b-960f-4f6d-be58-1ab2e477256a" />

[Link](https://www.youtube.com/watch?v=xfmdanZ_Fgc&t=907s)
