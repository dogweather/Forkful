---
title:                "YAML로 작업하기"
aliases:
- /ko/arduino/working-with-yaml/
date:                  2024-02-03T19:24:46.765569-07:00
model:                 gpt-4-0125-preview
simple_title:         "YAML로 작업하기"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/arduino/working-with-yaml.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 무엇 & 왜?

YAML(YAML Ain't Markup Language)은 구성 파일, 프로그램 간 통신 및 데이터 저장을 위해 사용할 수 있는 인간이 읽을 수 있는 데이터 직렬화 표준입니다. 프로그래머들은 애플리케이션의 구성 과정을 간소화하고, 코드를 깊이 파고들지 않고도 매개변수를 수정하기 쉽게 하며, 가독성을 향상시키고 구성 공유를 간단하게 만들기 위해 아두이노 프로젝트에 YAML을 사용합니다.

## 방법:

아두이노에서 YAML을 직접 작업하는 것은 메모리 제약과 네이티브 YAML 처리 라이브러리의 부재로 인해 고수준 프로그래밍 환경에서처럼 간단하지 않습니다. 그러나 YAML 파싱이나 생성이 필요한 프로젝트의 경우, 일반적인 접근 방법은 유닛 컴퓨터(예: 라즈베리 파이)를 사용하거나 외부 스크립트를 사용하여 YAML 파일을 더 아두이노 친화적인 형식(예: JSON)으로 변환하는 것입니다. 시연 목적으로, 우리는 인기 있는 라이브러리인 ArduinoJson을 사용하여 후자의 접근 방식에 집중하겠습니다.

**1단계:** YAML 구성을 JSON으로 변환합니다. 온라인 도구나 `yq`와 같은 커맨드 라인 유틸리티를 사용할 수 있습니다.

YAML 파일 (`config.yaml`):
```yaml
wifi:
  ssid: "YourSSID"
  password: "YourPassword"
```

JSON으로 변환됨 (`config.json`):
```json
{
  "wifi": {
    "ssid": "YourSSID",
    "password": "YourPassword"
  }
}
```

**2단계:** ArduinoJson 라이브러리를 사용하여 아두이노 스케치에서 JSON 파일을 파싱합니다. 먼저 아두이노 IDE의 라이브러리 관리자를 통해 ArduinoJson 라이브러리를 설치해야 합니다.

**3단계:** 코드에서 JSON을 로드하고 파싱합니다. 아두이노의 저장 공간 제한으로 인해, JSON 문자열이 변수에 저장되었다고 가정하거나 SD 카드에서 읽는 것을 상상해 보세요.

샘플 아두이노 스케치:
```cpp
#include <ArduinoJson.h>

const char* jsonConfig = "{\"wifi\":{\"ssid\":\"YourSSID\",\"password\":\"YourPassword\"}}";

void setup() {
  Serial.begin(9600);

  StaticJsonDocument<200> doc;
  DeserializationError error = deserializeJson(doc, jsonConfig);

  if (error) {
    Serial.print(F("deserializeJson() 실패: "));
    Serial.println(error.f_str());
    return;
  }

  const char* ssid = doc["wifi"]["ssid"]; // "YourSSID"
  const char* password = doc["wifi"]["password"]; // "YourPassword"

  Serial.print("SSID: ");
  Serial.println(ssid);
  Serial.print("Password: ");
  Serial.println(password);
}

void loop() {
  // 이 예제에서는 여기에 아무것도 없습니다
}
```

스케치를 실행했을 때의 출력:
```
SSID: YourSSID
Password: YourPassword
```

JSON으로 전환하고 ArduinoJson 라이브러리를 활용하는 이 접근 방식을 통해 아두이노 프로젝트 내에서 관리 가능한 YAML 구성 처리를 가능하게 하여, 마이크로컨트롤러에서의 직접적인 YAML 파싱을 회피할 수 있습니다.
