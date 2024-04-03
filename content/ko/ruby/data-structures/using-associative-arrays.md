---
changelog:
- 2024-01-30, gpt-4-0125-preview, translated from English
date: 2024-01-30 19:13:13.865041-07:00
description: "\uC5F0\uAD00 \uBC30\uC5F4\uC740 Ruby\uC5D0\uC11C\uB294 \uC77C\uBC18\uC801\
  \uC73C\uB85C \uD574\uC2DC\uB77C\uACE0 \uC54C\uB824\uC838 \uC788\uC73C\uBA70, \uACE0\
  \uC720\uD55C \uD0A4\uB97C \uAC12\uACFC \uC5F0\uACB0\uD560 \uC218 \uC788\uAC8C \uD574\
  \uC90D\uB2C8\uB2E4. \uD2B9\uC815 \uCC38\uC870\uB97C \uD1B5\uD574 \uC694\uC18C\uB97C\
  \ \uCD94\uC801\uD558\uAC70\uB098 \uAC1D\uCCB4\uC758 \uC18D\uC131\uC744 \uC800\uC7A5\
  \uD558\uAC70\uB098 \uACE0\uC720 \uC2DD\uBCC4\uC790\uB85C \uB370\uC774\uD130\uC5D0\
  \ \uBE60\uB974\uAC8C \uC811\uADFC\uD560 \uD544\uC694\uAC00 \uC788\uC744 \uB54C \uC5C6\
  \uC5B4\uC11C\uB294 \uC548\uB420 \uC911\uC694\uD55C \uAE30\uB2A5\uC785\uB2C8\uB2E4\
  ."
lastmod: '2024-03-13T22:44:55.981453-06:00'
model: gpt-4-0125-preview
summary: "\uC5F0\uAD00 \uBC30\uC5F4\uC740 Ruby\uC5D0\uC11C\uB294 \uC77C\uBC18\uC801\
  \uC73C\uB85C \uD574\uC2DC\uB77C\uACE0 \uC54C\uB824\uC838 \uC788\uC73C\uBA70, \uACE0\
  \uC720\uD55C \uD0A4\uB97C \uAC12\uACFC \uC5F0\uACB0\uD560 \uC218 \uC788\uAC8C \uD574\
  \uC90D\uB2C8\uB2E4."
title: "\uC5F0\uAD00 \uBC30\uC5F4 \uC0AC\uC6A9\uD558\uAE30"
weight: 15
---

## 방법:
Ruby에서 해시를 생성하고 사용하는 것은 간단합니다. 비어 있는 해시를 초기화하고, 키-값 쌍으로 채우고, 키로 값을 접근하고, 그 외의 다른 작업을 할 수 있습니다. 다음은 그 방법입니다:

```Ruby
# 해시 생성하기
my_hash = { "name" => "John Doe", "age" => 30 }

# 다른 방법으로 해시 만들기
another_hash = Hash.new
another_hash["position"] = "Developer"

# 해시 값에 접근하기
puts my_hash["name"] # 출력: John Doe

# 새로운 키-값 쌍 추가하기
my_hash["language"] = "Ruby"
puts my_hash # 출력: {"name"=>"John Doe", "age"=>30, "language"=>"Ruby"}

# 해시를 통해 반복하기
my_hash.each do |key, value|
  puts "#{key}: #{value}"
end
# 출력:
# name: John Doe
# age: 30
# language: Ruby
```

키로 더 효율적인 심볼을 사용할 수도 있습니다:

```Ruby
# 키로 심볼 사용하기
symbol_hash = { name: "Jane Doe", age: 22 }
puts symbol_hash[:name] # 출력: Jane Doe
```

## 심층 탐구:
연관 배열의 개념은 Ruby에만 국한된 것이 아니며, 많은 언어들이 Python의 딕셔너리나 JavaScript의 객체(키-값 쌍으로 사용될 때)와 같은 여러 이름으로 이를 구현합니다. Ruby 초기 단계에서 해시는 다소 느리고 다양성이 떨어졌습니다. 하지만, 시간이 지나면서 Ruby의 해시 구현은 특히 심볼 키를 위해 매우 최적화되어 일반적인 접근과 업데이트를 위해 매우 효율적입니다.

Ruby의 해시는 그 사용의 문법적 용이성과 유연성에 있어서 두각을 나타냅니다 - 키로 거의 모든 객체 타입을 사용할 수 있지만, 심볼과 문자열이 가장 일반적입니다. 내부적으로, Ruby 해시는 속도와 메모리 효율성을 균형있게 유지하면서 요소의 수가 증가함에 따라 해싱 알고리즘을 사용하여 구현됩니다.

해시는 매우 다재다능하지만, Ruby에서 데이터 저장을 위한 만능 해결책은 아닙니다. 순서가 있는 컬렉션에는 배열이 더 적합하고, 유일한 항목의 집합에는 Set이 더 나은 선택일 수 있습니다. 또한, 매우 복잡한 데이터 구조의 경우, 사용자 정의 클래스를 만드는 것이 좋을 수도 있습니다.

기억하세요, 해시 사용과 다른 데이터 구조의 선택은 대부분 특정 사용 사례에 따라 달라집니다—해시는 빠른 조회와 고유한 키와 그 값 사이의 연관을 유지하는 데 뛰어납니다.
