---
title:                "문자열 보간하기"
aliases:
- ko/bash/interpolating-a-string.md
date:                  2024-01-20T17:50:36.937936-07:00
model:                 gpt-4-1106-preview
simple_title:         "문자열 보간하기"

tag:                  "Strings"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/bash/interpolating-a-string.md"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)
문자열 보간은 변수나 표현식의 값을 문자열 안으로 삽입하는 것입니다. 이를 통해 코드의 유연성을 높이고, 동적으로 데이터를 문자열에 결합할 수 있기 때문에 프로그래머들이 사용합니다.

## How to: (방법)
```Bash
# 변수 보간 사용 예
name="세종대왕"
greeting="안녕하세요, $name님!"
echo $greeting # 출력: 안녕하세요, 세종대왕님!

# 명령어 실행 결과를 문자열에 보간
user_count=$(who | wc -l)
echo "접속 중인 사용자 수: $user_count" # 출력: 접속 중인 사용자 수: 3
```

## Deep Dive (심층 분석)
문자열 보간은 Bash에서 `" "` 안에서 `$변수명`을 사용하며 변수의 값을 문자열에 삽입합니다. 1990년대 초반 Bash는 Bourne Again SHell로서, Steve Bourne의 'sh'에 기반해 만들어진 Brian Fox에 의해 시작됐습니다. "$변수명" 대신에 `${변수명}`을 사용하는 이유는 문자열과 변수명을 명확히 구분하기 위함입니다. 예를 들어, "file${number}.txt" 처럼 사용할 수 있습니다. 하위 호환을 위해 꼭 필요하지 않은 한 `"`대신 `'`을 쓰는 것보다는 `"`을 사용하는 것이 좋습니다.

대체 방법으로는 `printf` 명령어나 Here document를 사용할 수도 있습니다. 예를 들면:

```Bash
# printf 명령어 사용
printf "안녕하세요, %s님!\n" "$name"

# Here document 사용
cat << END
안녕하세요, $name님!
END
```

## See Also (추가 자료)
- Bash Manual: [https://www.gnu.org/software/bash/manual/](https://www.gnu.org/software/bash/manual/)
- Advanced Bash-Scripting Guide: [https://tldp.org/LDP/abs/html/](https://tldp.org/LDP/abs/html/)
