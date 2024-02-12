---
title:                "디버거 사용하기"
aliases:
- /ko/arduino/using-a-debugger/
date:                  2024-01-26T03:48:29.735758-07:00
model:                 gpt-4-0125-preview
simple_title:         "디버거 사용하기"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/arduino/using-a-debugger.md"
---

{{< edit_this_page >}}

## 무엇인가 & 왜인가?

디버거는 코드 속 버그를 짜내는 데 도움을 주는 도구입니다. 코드 실행을 일시 중지하고, 주변을 살펴보며, 실제로 무슨 일이 벌어지고 있는지 알 수 있게 해줍니다. 프로그래머들은 자신의 코드를 단계별로 진행하면서 변수를 검사하고 문제가 발생할 수 있는 위치를 이해하기 위해 디버거를 사용합니다.

## 방법:

Arduino IDE를 사용할 때는 시리얼 출력을 사용하여 디버깅할 수 있지만, 이는 동굴 탐험에 손전등을 사용하는 것과 비슷합니다. 실제 디버깅을 위해서는 Atmel-ICE 디버거와 같이 Arduino 환경과 통합되는 것을 사용하는 것이 좋습니다. 시리얼을 사용한 유사 디버깅의 예는 다음과 같습니다:

```Arduino
void setup() {
  Serial.begin(9600);
}
void loop() {
  int sensorValue = analogRead(A0);
  Serial.print("센서 값: ");
  Serial.println(sensorValue);
  // 여기서 512를 기대하고 있지만 0이 나온다면,
  // 센서 연결을 검사할 시간
  delay(1000); // 다시 읽기 전에 1초 동안 대기
}
```
이것을 시리얼 모니터에서 실행하면 센서가 실시간으로 내뱉는 것을 볼 수 있습니다.

## 심층 탐구

디버거가 등장하기 전에는 print 문의 세계였습니다 – 모든 것을 출력하여 일어나는 일을 추측할 수밖에 없었습니다. 프린트를 사용한 디버깅은 여전히 흔하며, 특히 Arduino와 같이 제약된 하드웨어나 간단한 환경에서는 그렇습니다.

Atmel-ICE와 같은 인-서킷 에뮬레이터에 대한 대안으로는 `avr-gdb`와 같은 소프트웨어 디버깅 도구가 있습니다. `avarice`와 짝을 이뤄 GDB와 하드웨어 사이의 다리를 만들 수 있어 칩 위에서 보다 고급 디버깅에 매우 유용합니다.

디버거를 사용하면 특정 지점에서 실행을 중지시킬 수 있는 중단점을 설정할 수 있습니다. 코드를 한 줄씩 진행하고, 메모리, 레지스터, 변수를 검사할 수 있습니다. 이를 통해 암흑 속에서의 막연한 시도 대신 문제를 정확히 지적할 수 있습니다. 디버거를 구현할 때는 환경이 올바르게 설정되어 있는지 확인하세요 - 버전 불일치나 잘못 구성된 도구는 좌절감을 초래할 수 있습니다.

## 참고 자료

더 깊이 탐구하고 싶으신가요? 다음을 참고하세요:
- [Arduino 디버깅 가이드](https://www.arduino.cc/en/Guide/Environment#toc7)
- avr-gdb 설정을 위한 AVR Libc 참조 매뉴얼: [AVR Libc 홈페이지](http://www.nongnu.org/avr-libc/)
