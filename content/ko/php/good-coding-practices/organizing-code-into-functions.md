---
date: 2024-01-26 01:11:10.521242-07:00
description: "\uCF54\uB4DC\uB97C \uD568\uC218\uB85C \uC870\uC9C1\uD654\uD558\uB294\
  \ \uAC83\uC740 \uC815\uC758\uB41C \uBAA9\uC801\uC744 \uAC00\uC9C4 \uC7AC\uC0AC\uC6A9\
  \ \uAC00\uB2A5\uD55C \uBE14\uB85D\uC73C\uB85C \uCF54\uB4DC\uB97C \uB098\uB204\uB294\
  \ \uAC83\uC5D0 \uB300\uD55C \uAC83\uC785\uB2C8\uB2E4. \uC774\uB294 \uCF54\uB4DC\uB97C\
  \ \uAE54\uB054\uD558\uAC8C \uC720\uC9C0\uD558\uACE0, \uC911\uBCF5\uC744 \uBC29\uC9C0\
  \uD558\uACE0, \uB514\uBC84\uAE45\uC744 \uC27D\uAC8C \uD558\uAE30 \uC704\uD574 \uC218\
  \uD589\uB429\uB2C8\uB2E4."
lastmod: '2024-03-13T22:44:55.364714-06:00'
model: gpt-4-1106-preview
summary: "\uCF54\uB4DC\uB97C \uD568\uC218\uB85C \uC870\uC9C1\uD654\uD558\uB294 \uAC83\
  \uC740 \uC815\uC758\uB41C \uBAA9\uC801\uC744 \uAC00\uC9C4 \uC7AC\uC0AC\uC6A9 \uAC00\
  \uB2A5\uD55C \uBE14\uB85D\uC73C\uB85C \uCF54\uB4DC\uB97C \uB098\uB204\uB294 \uAC83\
  \uC5D0 \uB300\uD55C \uAC83\uC785\uB2C8\uB2E4."
title: "\uCF54\uB4DC\uB97C \uD568\uC218\uB85C \uAD6C\uC131\uD558\uAE30"
weight: 18
---

## 어떻게:
사용자에게 인사하는 반복적인 코드가 있다고 상상해 봅시다. 대신, 이를 `greet_user`라는 함수로 감쌀 것입니다:

```php
function greet_user($name) {
    return "Hello, " . $name . "!";
}

echo greet_user("Alice");
echo greet_user("Bob");
```

출력 결과:
```
Hello, Alice!
Hello, Bob!
```

이제, 인사하는 동일한 코드를 매번 다시 작성하지 않고 언제든 사용할 수 있는 편리한 도구가 생겼습니다.

## 심층 탐구
함수는 '50년대 FORTRAN 초기부터 프로그래밍에 있었습니다. 구조화된 프로그래밍의 기초이며 모듈성과 분리에 관한 것입니다. 대안이라면? 객체 지향을 활용하여 클래스와 메서드(기능적으로 멋진 정장을 입은 함수들)에 대해 이야기할 수 있습니다. PHP의 경우, 구현 세부 사항에는 매개변수의 기본값 지정, 입력에 대한 타입 힌팅, 배열이나 PHP 7.1부터는 리스트를 사용하여 여러 값을 반환할 수 있음을 포함합니다.

여기 타입 선언과 기본값을 사용한 현대적인 변주가 있습니다:

```php
function add(float $a, float $b = 0.0): float {
    return $a + $b;
}

echo add(1.5);
echo add(1.5, 2.5);
```

PHP 7.4는 배열 연산에서 일반적으로 사용되는 간결한 일 줄 함수를 작성하는 데 도움이 되는 화살표 함수도 도입했습니다:

```php
$numbers = array(1, 2, 3, 4);
$squared = array_map(fn($n) => $n * $n, $numbers);
print_r($squared);
```

출력 결과:
```
Array
(
    [0] => 1
    [1] => 4
    [2] => 9
    [3] => 16
)
```

## 참조
- [함수에 대한 PHP 매뉴얼](https://www.php.net/manual/en/functions.user-defined.php)
- [PHP: 올바른 방법 - 함수](https://phptherightway.com/#functions)
- [PHP 7.4 화살표 함수에 대해 알아보기](https://stitcher.io/blog/short-closures-in-php)
