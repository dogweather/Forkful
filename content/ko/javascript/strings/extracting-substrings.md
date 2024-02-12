---
title:                "부분 문자열 추출"
aliases:
- /ko/javascript/extracting-substrings/
date:                  2024-01-20T17:45:59.706072-07:00
model:                 gpt-4-1106-preview
simple_title:         "부분 문자열 추출"

tag:                  "Strings"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/javascript/extracting-substrings.md"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)
JavaScript에서 문자열의 일부를 추출하는 것은 특정 부분의 데이터를 얻기 위함입니다. 검색, 데이터 정제 또는 UI 표시와 같은 많은 작업에 필수적입니다.

## How to (방법):
```Javascript
// substring() 사용
let text = "Hello, JavaScript!";
let part = text.substring(7, 19); // "JavaScript!"
console.log(part);

// slice() 사용
part = text.slice(7, 19); // "JavaScript!"
console.log(part);

// substr() 사용 (비권장)
part = text.substr(7, 12); // "JavaScript!"
console.log(part);
```
출력:
```
JavaScript!
JavaScript!
JavaScript!
```

## Deep Dive (심층 분석):
substring, slice, 그리고 substr은 모두 JavaScript에서 문자열을 추출하는 방법입니다. substring과 slice는 매우 유사하지만 매개 변수에 음수가 들어갈 경우의 행동이 다릅니다. substr은 현재는 권장되지 않으며 추후 표준에서 제거될 예정입니다. 이러한 함수는 문자열 작업을 쉽고 효율적으로 만드는 중요한 도구입니다.

## See Also (참조):
- MDN Web Docs substring(): https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring
- MDN Web Docs slice(): https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice
- MDN Web Docs substr(): https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substr (단, 이 링크는 이 함수가 더 이상 권장되지 않음을 알립니다)
