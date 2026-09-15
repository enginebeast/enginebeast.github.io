---
title: "Introduction to Raspberry Pi"
categories:
  - car_project
---

### Troubleshooting Raspberry Pi Wi-Fi Connection Issues
라즈베리파이 os를 설치한 SD카드를 삽입하고 메인 데스크탑과 라즈베리파이 보드의 연결을 시도한 나는 상당히 당황했다. 분명 인터넷 자료에서도 라즈베리파이브5 자체에 내장 와이파이가 장착되어 있다고 나오는데 pc는 라즈베리파이를 잡지 못하고 있었기 때문이다.

우선 처음에는 SD 카드가 불량인가 하였지만 이 가설은 금방 기각되었다. 애초에 SD 카드가 불량이라면 SD 카드 리더기에 꽂았을 때부터 인식을 제대로 할리가 없었기 때문이다.

두번째로 생각한 것은 OS 설치 때 설정을 잘못했나였지만 OS imager를 눌러 설정을 여러번 뒤져봐도 설정에 큰 문제는 없었다.

세번째로 알아낸 것은 라즈베리파이5에 자체적으로 와이파이가 장착되어 있는 것은 맞지만 처음에는 인식하지 못하는 케이스가 많고 유선으로 연결해줘야 한다는 정보였다. 하지만 유선 연결 후에도 문제는 제대로 해결되지 않았고 애초에 스크린으로 결과를 확인할 수 없기에 유선으로도 제대로 연결되어 있는지 알 수 없었다.

결국 최종적으로 마이크로 HDMI 랜선을 주문하여 메인데스크탑에 연결해 쓰던 스크린에 연결해 문제 원인을 파악할 수밖에 없었다. 애초에 라즈베리파이는 SD 카드를 인식하지 못하고 있었다. 그렇지만 첫번째 가설에서 SD 카드 자체의 불량은 없었으니 문제는 보드에 있다고 추측할 수 있었다. 

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

이후 주문한 케이블로 바꿔서 연결해 확인해본 결과 카메라가 제대로 화면을 포착하고 있는 것을 확인할 수 있었다. 하지만 원거리 통신이라 화면의 반응이 느려서 메인 데스크탑의 스크린과 따로 쓸 수 있는 스크린의 필요성이 절실하다고 느꼈다.