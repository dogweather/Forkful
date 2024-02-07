---
title:                "텍스트 파일 읽기"
date:                  2024-01-20T17:53:30.875202-07:00
model:                 gpt-4-1106-preview
simple_title:         "텍스트 파일 읽기"

tag:                  "Files and I/O"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/arduino/reading-a-text-file.md"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)
텍스트 파일 읽기란, 글자가 쓰여진 파일을 가져와 프로그램에서 사용할 수 있는 데이터로 만드는 과정이다. 프로그래머들은 설정, 데이터 처리, 혹은 소프트웨어 간 통신을 위해 이 작업을 한다.

## How to: (방법)
아두이노에선 SD 카드 모듈을 사용해 텍스트 파일을 읽을 수 있다. 간단한 예제를 살펴보자.

```Arduino
#include <SD.h>
#include <SPI.h>

void setup() {
  Serial.begin(9600);
  while (!Serial) {
    ; // wait for serial port to connect.
  }

  if (!SD.begin(4)) {
    Serial.println("SD card initialization failed!");
    return;
  }
  
  File dataFile = SD.open("example.txt");
  if (dataFile) {
    while (dataFile.available()) {
      Serial.write(dataFile.read());
    }
    dataFile.close();
  } else {
    Serial.println("File open failed!");
  }
}

void loop() {
  // Nothing here
}
```
파일에 있는 내용이 시리얼 모니터에 표시된다.

## Deep Dive (심층 분석)
텍스트 파일 읽기 기능은 아두이노에서 다양한 프로젝트에 활용되며, 역사적으로는 punched tape에서 시작하여 디지털 저장 매체로 발전했다. SD 카드 모듈 사용은 가장 일반적인 방법이지만, EEPROM이나 인터넷을 통한 데이터 접근 방식도 있다. 데이터 형식에 따라 read(), readBytes(), readString() 등 다양한 함수를 사용하여 구현할 수 있다.

## See Also (참고 자료)
- 아두이노 공식 SD 라이브러리 문서: [Arduino - SD](https://www.arduino.cc/en/Reference/SD)
- SPI 라이브러리 소개: [Arduino - SPI](https://www.arduino.cc/en/Reference/SPI)
- EEPROM 읽기와 쓰기: [Arduino - EEPROMRead](https://www.arduino.cc/en/Tutorial/EEPROMRead)
