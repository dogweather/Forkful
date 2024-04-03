---
date: 2024-01-20 17:46:22.019039-07:00
description: "\uBB38\uC790\uC5F4\uC5D0\uC11C \uBD80\uBD84 \uBB38\uC790\uC5F4\uC744\
  \ \uCD94\uCD9C\uD558\uB294 \uAC83\uC740 \uD2B9\uC815 \uC870\uAC01\uC744 \uB5BC\uC5B4\
  \uB0B4\uB294 \uC791\uC5C5\uC785\uB2C8\uB2E4. \uB370\uC774\uD130\uB97C \uD30C\uC2F1\
  \uD558\uAC70\uB098 \uBD84\uC11D\uD560 \uB54C \uD544\uC694\uD55C \uC815\uBCF4\uB9CC\
  \ \uCDE8\uD558\uAE30 \uC704\uD574 \uD504\uB85C\uADF8\uB798\uBA38\uB4E4\uC774 \uC790\
  \uC8FC \uC0AC\uC6A9\uD569\uB2C8\uB2E4."
isCJKLanguage: true
lastmod: '2024-03-13T22:44:55.341554-06:00'
model: gpt-4-1106-preview
summary: "\uBB38\uC790\uC5F4\uC5D0\uC11C \uBD80\uBD84 \uBB38\uC790\uC5F4\uC744 \uCD94\
  \uCD9C\uD558\uB294 \uAC83\uC740 \uD2B9\uC815 \uC870\uAC01\uC744 \uB5BC\uC5B4\uB0B4\
  \uB294 \uC791\uC5C5\uC785\uB2C8\uB2E4."
title: "\uBD80\uBD84 \uBB38\uC790\uC5F4 \uCD94\uCD9C"
weight: 6
---

## How to: (어떻게 하나요?)
PHP에서 문자열의 일부를 추출할 땐 `substr` 함수를 사용합니다. 보기 쉽게 아래에 코드 예제와 실행 결과를 함께 두었습니다.

```php
$text = "안녕하세요, PHP를 배우고 계시는군요!";

// substr로 문자열의 일부 추출
$greeting = substr($text, 0, 5);
echo $greeting; // 출력: 안녕하세요

// 음수 인덱스로 뒤에서부터 추출
$learning = substr($text, -6);
echo $learning; // 출력: 배우고 계시는군요!
```

## Deep Dive (심층 분석)
`substr`은 PHP 4 때부터 사용되었고, 현재 PHP 8에서도 사용됩니다. 문자열 처리는 프로그래밍에서 중요한 부분을 차지하므로 다양한 방식으로 개선되어 왔습니다.

대안으로는 `mb_substr` 함수가 있는데, 다국어를 처리할 때 주로 사용합니다. UTF-8 같은 멀티바이트 문자 인코딩을 정확히 다루기 위함입니다.

구현 세부사항으로는, `substr`이 내부적으로 문자열의 포인터를 조정하여 필요한 부분만 반환한다는 점입니다. 이는 성능 최적화에 기여합니다.

## See Also (관련 자료)
- [PHP: substr - Manual](https://www.php.net/manual/en/function.substr.php)
- [PHP: mb_substr - Manual](https://www.php.net/manual/en/function.mb-substr.php)
- [UTF-8 - Wikipedia](https://en.wikipedia.org/wiki/UTF-8)
