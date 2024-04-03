---
changelog:
- 2024-01-30, gpt-4-0125-preview, translated from English
date: 2024-01-30 19:10:43.933255-07:00
description: "C++\uC5D0\uC11C `std::map` \uB610\uB294 `std::unordered_map`\uC73C\uB85C\
  \ \uC54C\uB824\uC9C4 \uC5F0\uAD00 \uBC30\uC5F4\uC740 \uBC30\uC5F4 \uC778\uB371\uC2A4\
  \uC640 \uC2E4\uC81C \uB370\uC774\uD130 \uC0AC\uC774\uC758 \uAC04\uACA9\uC744 \uBA54\
  \uC6B0\uBA70 \uC758\uBBF8 \uC788\uB294 \uD0A4\uB97C \uC0AC\uC6A9\uD560 \uC218 \uC788\
  \uAC8C \uD574\uC90D\uB2C8\uB2E4. \uC778\uB371\uC2A4 \uC704\uCE58 \uB300\uC2E0 \uD0A4\
  \uB97C \uC0AC\uC6A9\uD558\uC5EC \uBE60\uB978 \uC870\uD68C, \uC0BD\uC785, \uC0AD\uC81C\
  \uAC00 \uD544\uC694\uD560 \uB54C \uC8FC\uB85C \uC0AC\uC6A9\uD569\uB2C8\uB2E4."
lastmod: '2024-03-13T22:44:55.657974-06:00'
model: gpt-4-0125-preview
summary: "C++\uC5D0\uC11C `std::map` \uB610\uB294 `std::unordered_map`\uC73C\uB85C\
  \ \uC54C\uB824\uC9C4 \uC5F0\uAD00 \uBC30\uC5F4\uC740 \uBC30\uC5F4 \uC778\uB371\uC2A4\
  \uC640 \uC2E4\uC81C \uB370\uC774\uD130 \uC0AC\uC774\uC758 \uAC04\uACA9\uC744 \uBA54\
  \uC6B0\uBA70 \uC758\uBBF8 \uC788\uB294 \uD0A4\uB97C \uC0AC\uC6A9\uD560 \uC218 \uC788\
  \uAC8C \uD574\uC90D\uB2C8\uB2E4."
title: "\uC5F0\uAD00 \uBC30\uC5F4 \uC0AC\uC6A9\uD558\uAE30"
weight: 15
---

## 사용 방법:
C++에서 연관 배열은 `<map>`과 `<unordered_map>` 헤더와 함께 사용됩니다. 두 가지 모두를 실제로 사용하는 예를 들어 보겠습니다.

### `std::map` 사용하기
`std::map`은 키를 기준으로 요소를 정렬된 상태로 유지합니다. 시작하는 방법은 다음과 같습니다:

```C++
#include <iostream>
#include <map>
#include <string>

int main() {
    std::map<std::string, int> ageMap;
    
    // 값 삽입
    ageMap["Alice"] = 30;
    ageMap["Bob"] = 25;
    
    // 값 접근
    std::cout << "Bob의 나이: " << ageMap["Bob"] << std::endl;
    
    // 맵 순회
    for(const auto &pair : ageMap) {
        std::cout << pair.first << "의 나이는 " << pair.second << "세 입니다." << std::endl;
    }
    
    return 0;
}
```

### `std::unordered_map` 사용하기
순서는 중요하지 않지만 성능은 중요할 때, `std::unordered_map`이 평균적으로 삽입, 조회, 삭제에 대해 더 빠른 복잡도를 제공하며 좋은 선택입니다.

```C++
#include <iostream>
#include <unordered_map>
#include <string>

int main() {
    std::unordered_map<std::string, double> productPrice;
    
    // 값 삽입
    productPrice["milk"] = 2.99;
    productPrice["bread"] = 1.99;
    
    // 값 접근
    std::cout << "우유 가격: $" << productPrice["milk"] << std::endl;
    
    // unordered_map 순회
    for(const auto &pair : productPrice) {
        std::cout << pair.first << "의 가격은 $" << pair.second << "입니다." << std::endl;
    }
    
    return 0;
}
```

## 심층 분석
C++의 연관 배열, 특히 `std::map`과 `std::unordered_map`은 요소를 저장하는 것 이상을 제공합니다. 검색, 삽입, 삭제와 같은 작업을 효율적인 시간 복잡도(로그 시간 복잡도로 `std::map` 및 평균적인 경우 상수 시간 복잡도로 `std::unordered_map`)로 허용함으로써 보다 복잡한 데이터 관리의 기반을 제공합니다. 이러한 효율성은 `std::map`의 경우 균형 트리, `std::unordered_map`의 경우 해시 테이블이라는 기본 데이터 구조에서 비롯됩니다.

역사적으로, 이러한 기능이 표준 라이브러리의 일부가 되기 전에는 프로그래머들이 자신의 버전을 구현하거나 타사 라이브러리를 사용해야 했으며, 이로 인해 일관성이 없고 잠재적인 비효율성이 발생했습니다. C++의 표준 라이브러리에 맵을 포함시킨 것은 그 사용을 표준화할 뿐만 아니라 다양한 컴파일러와 플랫폼에서 성능을 최적화했습니다.

두 가지 모두 강력하지만, `std::map`과 `std::unordered_map` 사이의 선택은 사용 사례의 구체적인 사항에 달려 있습니다. 순서가 있는 데이터가 필요하고 약간의 성능 저하를 감수할 수 있다면 `std::map`을 선택하세요. 속도가 중요하고 순서는 상관없다면 `std::unordered_map`이 더 나은 선택일 것입니다.

그러나, 복잡한 데이터 구조를 다룰 때는 항상 절충안이 존재한다는 점을 주의해야 합니다. 일부 특정 사례에서는 다른 데이터 구조나 타사 라이브러리가 특정 필요에 더 잘 맞는 성능이나 기능을 제공할 수도 있습니다. 프로젝트의 요구 사항에 기반하여 옵션을 항상 고려하세요.
