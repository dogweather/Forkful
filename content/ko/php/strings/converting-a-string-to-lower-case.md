---
date: 2024-01-20 17:39:17.179445-07:00
description: "\uBB38\uC790\uC5F4\uC744 \uC18C\uBB38\uC790\uB85C \uBCC0\uD658\uD558\
  \uB294 \uAC83\uC740 \uB300\uBB38\uC790\uAC00 \uD3EC\uD568\uB41C \uBB38\uC790\uC5F4\
  \uC744 \uC804\uBD80 \uC18C\uBB38\uC790\uB85C \uBC14\uAFB8\uB294 \uACFC\uC815\uC785\
  \uB2C8\uB2E4. \uD504\uB85C\uADF8\uB798\uBA38\uB4E4\uC740 \uB300\uC18C\uBB38\uC790\
  \ \uAD6C\uBD84 \uC5C6\uC774 \uAC80\uC0C9, \uC815\uB82C \uB4F1\uC758 \uC791\uC5C5\
  \uC744 \uD3B8\uD558\uAC8C \uD558\uAE30 \uC704\uD574 \uC774 \uC791\uC5C5\uC744 \uC218\
  \uD589\uD569\uB2C8\uB2E4."
isCJKLanguage: true
lastmod: '2024-03-13T22:44:55.338737-06:00'
model: gpt-4-1106-preview
summary: "\uBB38\uC790\uC5F4\uC744 \uC18C\uBB38\uC790\uB85C \uBCC0\uD658\uD558\uB294\
  \ \uAC83\uC740 \uB300\uBB38\uC790\uAC00 \uD3EC\uD568\uB41C \uBB38\uC790\uC5F4\uC744\
  \ \uC804\uBD80 \uC18C\uBB38\uC790\uB85C \uBC14\uAFB8\uB294 \uACFC\uC815\uC785\uB2C8\
  \uB2E4."
title: "\uBB38\uC790\uC5F4\uC744 \uC18C\uBB38\uC790\uB85C \uBCC0\uD658\uD558\uAE30"
weight: 4
---

## How to: (방법)
PHP에서 문자열을 소문자로 바꾸기 위해 `strtolower()` 함수를 사용할 수 있습니다. 사용 예시를 보여드리죠.

```PHP
<?php
$text = "Hello, World!";
$lowercaseText = strtolower($text);

echo $lowercaseText; // "hello, world!"
?>
```

`mb_strtolower()` 함수는 멀티바이트 문자(예: 한글)를 처리할 때 사용합니다.

```PHP
<?php
$korText = "안녕하세요, 세계!";
$lowercaseKorText = mb_strtolower($korText);

echo $lowercaseKorText; // "안녕하세요, 세계!"
?>
```

## Deep Dive (심층 분석)
처음에, PHP는 영문만을 대상으로 문자열을 소문자로 바꿨습니다. 하지만 글로벌 사용자가 증가하면서 `mb_string` 모듈이 등장했고, 다양한 문자 인코딩을 지원하기 시작했습니다. `strtolower()` 함수는 기본적인 영문자 외에는 대소문자 변환을 올바르게 처리하지 못할 수 있습니다. 그러므로 비영문 문자가 포함된 문자열에 대해서는 `mb_strtolower()` 함수를 사용해야 합니다. 이 함수에서는 적절한 인코딩을 지정할 수 있으며, 기본값은 `mb_internal_encoding()` 함수를 통해 설정된 내부 문자 인코딩입니다.

대안적으로, 문자열을 배열로 분해하고 개별 문자를 변환한 후 다시 문자열로 결합하는 방법이 있지만, 이는 불필요하게 복잡하고 성능 면에서도 비효율적입니다.

## See Also (관련 자료)
- [PHP String Functions](https://www.php.net/manual/en/ref.strings.php)
- [Multibyte String Functions](https://www.php.net/manual/en/ref.mbstring.php)
- [mb_strtolower() - PHP Manual](https://www.php.net/manual/en/function.mb-strtolower.php)
- [strtolower() - PHP Manual](https://www.php.net/manual/en/function.strtolower.php)
