youtube video :  https://youtu.be/PluRZjkgfys





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

## 💡 예제 2: 비트 카운터 (`bit_counter.sh`)

3개의 LED를 사용하여 0~7까지의 숫자를 이진수로 표현합니다.

- 사용 핀: GPIO 22, 23, 24 (3비트)
- 동작 방식:
  - 0부터 7까지의 숫자를 2진수로 변환하여 LED에 출력
  - 1초마다 숫자가 1씩 증가하며, LED 패턴도 변화
  - 3개의 LED가 2진수 디지털 카운터처럼 동작

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
