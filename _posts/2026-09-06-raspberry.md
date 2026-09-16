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

Finally I purchase the micro HDMI cable, and diagnose the cause of problem. At first, raspberry pi could not recognize SD card properly. However, in the first hypothesis, I checked there are no problem in SD card. So, I can supposed that the board has an error.

결국 최종적으로 마이크로 HDMI선을 주문하여 메인데스크탑에 연결해 쓰던 스크린에 연결해 문제 원인을 파악할 수밖에 없었다. 애초에 라즈베리파이는 SD 카드를 인식하지 못하고 있었다. 그렇지만 첫번째 가설에서 SD 카드 자체의 불량은 없었으니 문제는 보드에 있다고 추측할 수 있었다. 

<img width="500" height="600" alt="Image" src="https://github.com/user-attachments/assets/a460e977-d0a2-4eb1-8af8-e30ecdf5ea67" />

결국 SD 리더기에 SD 카드를 꽂고 그 리더기를 다시 USB 단자에 꽂고 나서야 SD 카드가 제대로 인식되기 시작했다. 배송 중에 고장난 것인지 내가 보드를 거칠게 다룬 것인지 알 수 없지만 SD 삽입 단자 자체가 불량이었던 것이다.

<img width="1000" height="500" alt="Image" src="https://github.com/user-attachments/assets/35377588-4804-42c2-b832-ad87481f36b3" />

이후 tigerVNC를 통해 확인한 라즈베리파이 화면은 위와 같다.

### Transferring and Running the Code on Raspberry Pi
<img width="600" height="650" alt="Image" src="https://github.com/user-attachments/assets/c0f724b3-7a85-4d2e-81ae-95e68357c763" />

<img width="600" height="600" alt="Image" src="https://github.com/user-attachments/assets/aff31cb6-abf8-45d8-94ed-ad527ac578b0" />

<img width="600" height="600" alt="Image" src="https://github.com/user-attachments/assets/803edc35-5e49-48ef-aa8b-936f49f6919c" />

이후 라즈베리파이에 데스크탑에 존재하는 Lane Detection 코드를 옮겨서 실행해보는 단계로 들어갔다. 처음에는 데스크탑에서 멀쩡히 돌아가는 코드가 라이브러리들을 다운로드해도 실행되지 않아 당황했다. 아마 라이브러리 내 메서드의 버전 차이 이슈로 보이며 chat GPT의 도움에 따라 내용을 수정했더니 정상적으로 작동하는 것을 확인할 수 있었다.

### Identifying the Camera Cable Compatibility Issue
<img width="600" height="800" alt="Image" src="https://github.com/user-attachments/assets/f40897ce-1ce7-448e-8a3f-48673bd58ec6" />

<img width="600" height="800" alt="Image" src="https://github.com/user-attachments/assets/b2b0eb3a-76cb-412c-add4-d188a8557ce9" />\

<img width="800" height="600" alt="Image" src="https://github.com/user-attachments/assets/908ca7da-0439-4519-8d2d-ace6869e12fb" />

<img width="600" height="600" alt="Image" src="https://github.com/user-attachments/assets/5380eff6-b9b5-4472-b5d0-43950fac2450" />

이후 주문한 케이블로 바꿔서 연결해 확인해본 결과 카메라가 제대로 작동하고 있는 것을 확인할 수 있었다. 하지만 원거리 통신이라 화면의 반응이 느려서 메인 데스크탑의 스크린과 따로 쓸 수 있는 스크린의 필요성이 절실하다고 느꼈다.