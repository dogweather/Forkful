---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:17:59.968008-07:00
description: "PHP\uC5D0\uC11C \uC815\uADDC \uD45C\uD604\uC2DD(regex)\uC740 \uBB38\uC790\
  \uC5F4 \uB0B4\uC5D0\uC11C \uBB38\uC790 \uC870\uD569\uC744 \uC77C\uCE58\uC2DC\uD0A4\
  \uB294 \uB370 \uC0AC\uC6A9\uB418\uB294 \uD328\uD134\uC73C\uB85C, \uC815\uAD50\uD55C\
  \ \uAC80\uC0C9 \uBC0F \uAD50\uCCB4 \uC791\uC5C5\uACFC \uB370\uC774\uD130 \uAC80\uC99D\
  \uC744 \uAC00\uB2A5\uD558\uAC8C \uD569\uB2C8\uB2E4. \uD504\uB85C\uADF8\uB798\uBA38\
  \uB294 \uD14D\uC2A4\uD2B8 \uD30C\uC2F1, \uC591\uC2DD \uAC80\uC99D, \uC6F9 \uB370\
  \uC774\uD130 \uC2A4\uD06C\uB798\uD551 \uB4F1\uC5D0 \uC788\uC5B4 \uADF8 \uAC15\uB825\
  \uD568\uACFC \uC720\uC5F0\uC131 \uB54C\uBB38\uC5D0 regex\uB97C\u2026"
lastmod: '2024-03-13T22:44:55.342998-06:00'
model: gpt-4-0125-preview
summary: "PHP\uC5D0\uC11C \uC815\uADDC \uD45C\uD604\uC2DD(regex)\uC740 \uBB38\uC790\
  \uC5F4 \uB0B4\uC5D0\uC11C \uBB38\uC790 \uC870\uD569\uC744 \uC77C\uCE58\uC2DC\uD0A4\
  \uB294 \uB370 \uC0AC\uC6A9\uB418\uB294 \uD328\uD134\uC73C\uB85C, \uC815\uAD50\uD55C\
  \ \uAC80\uC0C9 \uBC0F \uAD50\uCCB4 \uC791\uC5C5\uACFC \uB370\uC774\uD130 \uAC80\uC99D\
  \uC744 \uAC00\uB2A5\uD558\uAC8C \uD569\uB2C8\uB2E4."
title: "\uC815\uADDC \uD45C\uD604\uC2DD \uC0AC\uC6A9\uD558\uAE30"
weight: 11
---

## 사용 방법:
PHP는 PCRE(Perl 호환 정규 표현식) 라이브러리를 통해 정규 표현식을 지원하며, 풍부한 함수 세트를 제공합니다. 사용 방법은 다음과 같습니다:

### 패턴 일치:
문자열 내에 패턴이 존재하는지 확인하려면 `preg_match()`를 사용합니다. 이 함수는 문자열에 패턴이 발견되면 1을, 발견되지 않으면 0을 반환합니다.

```php
if (preg_match("/\bweb\b/i", "PHP는 웹 스크립팅 언어입니다")) {
    echo "일치하는 항목이 발견되었습니다.";
} else {
    echo "일치하는 항목이 발견되지 않았습니다.";
}
// 출력: 일치하는 항목이 발견되었습니다.
```

### 모든 일치 항목 찾기:
문자열 내에 패턴의 모든 발생을 찾아야 할 때 `preg_match_all()`이 사용됩니다.

```php
$text = "고양이와 개";
$pattern = "/\b([a-z]+)\b/i";
preg_match_all($pattern, $text, $matches);
print_r($matches[0]);
// 출력: Array ( [0] => 고양이 [1] => 와 [2] => 개 )
```

### 텍스트 교체:
정규 표현식과 일치하는 텍스트를 교체하기 위해 `preg_replace()`가 사용됩니다. 데이터 포맷팅 및 정리에 매우 강력합니다.

```php
$originalText = "2003년 4월 15일";
$pattern = "/(\w+) (\d+), (\d+)/i";
$replacement = '${1}1,$3';
echo preg_replace($pattern, $replacement, $originalText);
// 출력: 2003년 4월1,15
```

### 문자열 분리:
`preg_split()`을 사용하여 문자열을 배열로 분리할 수 있으며, 구분자에 대한 패턴을 지정합니다.

```php
$text = "PHP는, 매우 인기 있는, 스크립팅 언어입니다";
$parts = preg_split("/,\s*/", $text);
print_r($parts);
// 출력: Array ( [0] => PHP는 [1] => 매우 인기 있는 [2] => 스크립팅 언어입니다 )
```

또한, 복잡한 정규 표현식 패턴과 작업을 위해 Symfony의 `Finder` 컴포넌트나 Laravel의 도우미 함수 모음과 같은 프레임워크와 라이브러리가 보다 편리한 추상화 계층을 제공할 수 있습니다. 그러나 PHP 스크립트 내에서 효율적인 텍스트 처리와 유효성 검사를 직접 수행하기 위해서는 PHP의 내장 PCRE 함수를 이해하고 활용하는 것이 중요합니다.
