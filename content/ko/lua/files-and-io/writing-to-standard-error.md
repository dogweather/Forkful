---
title:                "표준 에러에 쓰기"
aliases:
- ko/lua/writing-to-standard-error.md
date:                  2024-02-03T19:33:53.973779-07:00
model:                 gpt-4-0125-preview
simple_title:         "표준 에러에 쓰기"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/lua/writing-to-standard-error.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 무엇 & 왜?
표준 오류(stderr)에 쓰기는 오류 메시지와 진단 출력을 표준 출력(stdout)과 다른 별도의 채널로 전송하는 것에 관한 것입니다. 프로그래머들은 일반 프로그램 결과와 오류 정보를 구별하고, 디버깅 및 로깅 프로세스를 간소화하기 위해 이렇게 합니다.

## 방법:
Lua에서는 `io.stderr:write()` 함수를 사용하여 stderr에 쓸 수 있습니다. 다음은 간단한 오류 메시지를 표준 오류에 쓰는 방법입니다:

```lua
io.stderr:write("Error: Invalid input.\n")
```

변수를 출력하거나 여러 데이터 조각을 결합해야 하는 경우, write 함수 내에서 이들을 연결하세요:

```lua
local errorMessage = "Invalid input."
io.stderr:write("Error: " .. errorMessage .. "\n")
```

**stderr에서의 샘플 출력:**
```
Error: Invalid input.
```

더 복잡한 시나리오나 더 큰 애플리케이션을 다룰 때는 LuaLogging과 같은 타사 로깅 라이브러리를 고려할 수 있습니다. LuaLogging을 사용하면 로그를 stderr를 포함한 다양한 목적지로 지정할 수 있습니다. 다음은 간략한 예시입니다:

먼저, LuaRocks를 사용하여 LuaLogging이 설치되어 있는지 확인하세요:

```
luarocks install lualogging
```

그런 다음, LuaLogging을 사용하여 stderr에 오류 메시지를 작성하려면:

```lua
local logging = require("logging")
local logger = logging.stderr()
logger:error("Error: Invalid input.")
```

이 접근 방식은 간단한 API를 통해 로그 레벨(예: ERROR, WARN, INFO)을 설정하는 추가적인 유연성을 제공하면서, 애플리케이션 전반에 걸쳐 표준화된 로깅의 이점을 제공합니다.
