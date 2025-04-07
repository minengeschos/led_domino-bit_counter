youtube video :  https://youtu.be/PluRZjkgfys     영상을 한번에 촬영하여서 2개의 영상 모두 같은 영상입니다.





회로도(GPIO 핀이 없는 관계로 아두이노로 대체 ==> 아두이노의 2,3,4,5번핀 == 22,23,24,25)
![image](https://github.com/user-attachments/assets/e9d092cf-80d8-4587-a01d-31360c34d2fa)

https://www.tinkercad.com/things/hFu7pd04CSS/editel?returnTo=%2Fdashboard%2Fdesigns%2Fcircuits



# Raspberry Pi GPIO LED 프로젝트

이 저장소는 Raspberry Pi 5의 GPIO 핀을 활용한 두 가지 LED 제어 예제(`led_domino`, `bit_counter`)를 담고 있습니다.  
제어는 모두 Bash 스크립트를 통해 이루어지며, `gpioset` 명령어를 이용하여 핀 상태를 직접 제어합니다.

---

## 🔧 준비 사항

- Raspberry Pi OS (Debian 기반)
- gpiod 패키지 설치:
  - `sudo apt update && sudo apt install gpiod -y`
- GPIO 핀 연결:
  - BCM 번호 기준 GPIO 22, 23, 24, 25번 사용
  - 각 핀은 330Ω 저항을 거쳐 LED의 양극(+)에 연결
  - LED의 음극(-)은 GND에 연결

---

## 💡 예제 1: LED 도미노 (`led_domino.sh`)

4개의 LED가 도미노처럼 차례대로 켜졌다가 꺼지는 효과를 구현합니다.

- 사용 핀: GPIO 22, 23, 24, 25
- 동작 방식:
  - 각 LED를 1초 동안 켰다가 끄고 다음 LED로 넘어감
  - 이 과정을 반복하여 도미노처럼 차례로 점등
- 무한 루프 형태로 반복 실행


---

## ▶️ 실행 방법

1. 스크립트에 실행 권한 부여
   - `chmod +x led_domino.sh`
   - `chmod +x bit_counter.sh`

2. 실행
   - `./led_domino.sh`
   - `./bit_counter.sh`

> 실행 중지: `Ctrl + C`

---

## 📌 참고

- 대부분의 Raspberry Pi에서는 GPIO 컨트롤러 이름이 `gpiochip0`입니다.
- 정확한 GPIO 정보는 `gpioinfo` 명령어로 확인 가능합니다.

---
