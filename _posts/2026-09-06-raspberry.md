---
title: "Introduction to Raspberry Pi"
categories:
  - car_project
---

### Troubleshooting Raspberry Pi Wi-Fi Connection Issues
I ran into some issues while trying to connect my main desktop to the Raspberry Pi. My PC could not detect the Raspberry Pi, even though online sources stated that the Raspberry Pi 5 has built-in Wi-Fi.

First, I thought the SD card might be faulty, but this hypothesis was quickly ruled out. If the SD card itself had been faulty, my PC would not have recognized it properly when I tried to write the OS image to it.

Second, I thought I might have made a mistake while installing the OS, but I could not find any major issues even after checking the Raspberry Pi Imager settings several times.

Third, I found that even though the Raspberry Pi 5 has built-in Wi-Fi, there are cases where it does not connect properly at first and may need to be connected via Ethernet. However, even after connecting it to the router with an Ethernet cable, the issue was not resolved. Since I had no screen connected to the Raspberry Pi, I could not even confirm whether the wired connection was working properly.

Finally, I had no choice but to order a micro-HDMI cable and connect the Raspberry Pi to the monitor I normally used with my main desktop in order to identify the cause of the problem. It turned out that the Raspberry Pi was not detecting the SD card properly. However, since I had already ruled out the possibility of a faulty SD card in my first hypothesis, I suspected that the problem might be with the board itself.

<img width="500" height="600" alt="Image" src="https://github.com/user-attachments/assets/a460e977-d0a2-4eb1-8af8-e30ecdf5ea67" />

After I inserted the SD card into the card reader and then plugged the reader into a USB port, the SD card was finally recognized properly. I could not tell whether the SD card slot had been damaged during shipping or whether I had handled the board too roughly, but the slot itself turned out to be faulty.

<img width="1000" height="500" alt="Image" src="https://github.com/user-attachments/assets/35377588-4804-42c2-b832-ad87481f36b3" />

The Raspberry Pi screen I checked through TigerVNC is shown above.

### Transferring and Running the Code on Raspberry Pi
<img width="600" height="650" alt="Image" src="https://github.com/user-attachments/assets/c0f724b3-7a85-4d2e-81ae-95e68357c763" />

<img width="600" height="600" alt="Image" src="https://github.com/user-attachments/assets/aff31cb6-abf8-45d8-94ed-ad527ac578b0" />

<img width="600" height="600" alt="Image" src="https://github.com/user-attachments/assets/803edc35-5e49-48ef-aa8b-936f49f6919c" />
Next, I moved the lane detection code from my main desktop to the Raspberry Pi and ran it. At first, I was confused because the code that ran perfectly on my desktop would not run on the Raspberry Pi, even after I installed the required libraries. Since the issue seemed to be caused by a version difference in the library, I modified some parts of the code with the help of ChatGPT, and it ran properly on the Raspberry Pi.

### Identifying the Camera Cable Compatibility Issue
<img width="600" height="800" alt="Image" src="https://github.com/user-attachments/assets/f40897ce-1ce7-448e-8a3f-48673bd58ec6" />

<img width="600" height="800" alt="Image" src="https://github.com/user-attachments/assets/b2b0eb3a-76cb-412c-add4-d188a8557ce9" />
이제 라즈베리파이 카메라가 제대로 작동하는지 연결하고 확인해보려 하는데 크기가 맞지 않아 꽂아지지 않았다. 알고 보니 내가 산 카메라에 세트로 있던 케이블인 15 pin to 15 pin 케이블이고 라즈베리파이5에 맞는 케이블은 15 pin to 22 pin 케이블이라는 것을 알게 되었다.

<img width="800" height="600" alt="Image" src="https://github.com/user-attachments/assets/908ca7da-0439-4519-8d2d-ace6869e12fb" />

<img width="600" height="600" alt="Image" src="https://github.com/user-attachments/assets/5380eff6-b9b5-4472-b5d0-43950fac2450" />

이후 주문한 케이블로 바꿔서 연결해 확인해본 결과 카메라가 제대로 작동하고 있는 것을 확인할 수 있었다. 하지만 원거리 통신이라 화면의 반응이 느려서 메인 데스크탑의 스크린과 따로 쓸 수 있는 스크린의 필요성이 절실하다고 느꼈다.