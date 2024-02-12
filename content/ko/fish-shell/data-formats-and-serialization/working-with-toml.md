---
title:                "프로그래머를 위한 TOML 다루기"
aliases:
- /ko/fish-shell/working-with-toml/
date:                  2024-01-26T04:21:43.926203-07:00
model:                 gpt-4-0125-preview
simple_title:         "프로그래머를 위한 TOML 다루기"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/fish-shell/working-with-toml.md"
---

{{< edit_this_page >}}

## 무엇 & 왜?
TOML은 사람이 읽고 쓰기 쉬우며 기계가 파싱하고 생성하기 쉬운 설정 파일 형식입니다. 프로그래머들은 가독성이 중요한 프로젝트에서 명확하고 계층적인 설정 파일을 위해 TOML을 사용합니다.

## 방법:
Fish에서 TOML을 읽고 조작하려면 TOML을 JSON으로 변환할 수 있는 `yj`와 같은 도구를 사용할 수 있습니다. 방법은 다음과 같습니다:

```fish
# Fisher를 통해 yj 설치
fisher install jorgebucaran/yj

# TOML을 JSON으로 변환
echo 'title = "TOML 예제"' | yj -tj

# 샘플 출력
{"title":"TOML 예제"}
```

TOML을 작성하려면, 과정을 반대로 실행합니다:

```fish
# JSON을 TOML로 변환
echo '{"title":"JSON 예제"}' | yj -jt

# 샘플 출력
title = "JSON 예제"
```

많은 양의 작업을 처리해야 한다면, `toml-cli`와 같은 전용 TOML CLI 도구를 고려해보세요.

```fish
# toml-cli 설치
pip install toml-cli

# TOML 파일에 값 설정
toml set pyproject.toml tool.poetry.version "1.1.4"

# TOML 파일에서 값 가져오기
set version (toml get pyproject.toml tool.poetry.version)
echo $version
```

## 심층 분석
TOML (Tom's Obvious, Minimal Language)은 2013년에 Tom Preston-Werner에 의해 소개되었으며, 정의된 사양과 데이터 계층 구조를 가진 INI와 유사합니다. 주요 대안으로는 JSON과 YAML이 있지만, 각각의 단점이 있습니다: JSON은 인간 친화적이지 않으며, YAML은 더 복잡합니다. TOML의 디자인은 설정 파일을 자주 수동으로 관리해야 하는 시나리오에서 번성하며, 단순성과 표현력 사이의 균형을 맞춥니다. 구현과 관련하여, 대부분의 프로그래밍 언어에 대한 TOML 파서가 사용 가능하며, 스크립트에 바로 통합될 수 있는 Fish 용 TomlBombadil도 포함됩니다.

## 참고자료
- TOML 공식 사양: https://toml.io
- `yj`, TOML, JSON, YAML, XML 간 변환을 위한 도구: https://github.com/jorgebucaran/yj
- `toml-cli`, TOML을 위한 커맨드라인 유틸리티: https://github.com/sdispater/toml-cli
