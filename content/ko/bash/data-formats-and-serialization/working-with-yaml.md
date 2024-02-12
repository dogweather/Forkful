---
title:                "YAML로 작업하기"
date:                  2024-02-03T19:24:51.547578-07:00
model:                 gpt-4-0125-preview
simple_title:         "YAML로 작업하기"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/bash/working-with-yaml.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 무엇 & 왜?

YAML은 "YAML Ain't Markup Language"의 약자로, 인간이 읽을 수 있는 데이터 직렬화 표준으로, 구성 파일 및 데이터가 저장되거나 전송되는 애플리케이션에서 사용할 수 있습니다. 프로그래머들은 복잡한 구성이 포함된 프로젝트나 쉽게 편집 가능한 데이터 구조가 필요할 때, 그 명확성과 단순성 때문에 YAML을 선호합니다.

## 방법:

Bash에서 YAML을 직접 다루기 위해서는 Bash가 YAML 파싱을 내장 지원하지 않기 때문에 약간의 재치가 필요합니다. 그러나 `yq`(경량이며 휴대가능한 커맨드라인 YAML 프로세서)와 같은 외부 도구를 사용하여 효율적으로 YAML 파일과 상호 작용할 수 있습니다. 몇 가지 일반적인 작업을 살펴봅시다:

### `yq` 설치:

예시를 다루기 전에, `yq`가 설치되어 있는지 확인하세요. 보통 패키지 매니저에서 설치할 수 있습니다. 예를 들어, 우분투에서는:

```bash
sudo apt-get install yq
```

또는 GitHub 저장소에서 직접 다운로드할 수 있습니다.

### 값을 읽기:

`config.yaml`이라는 파일이 있고 다음과 같은 내용이 있다고 가정해 보겠습니다:

```yaml
database:
  host: localhost
  port: 5432
user:
  name: admin
  password: secret
```

데이터베이스 호스트를 읽으려면 다음과 같이 `yq`를 사용할 수 있습니다:

```bash
yq e '.database.host' config.yaml
```

**샘플 출력:**

```
localhost
```

### 값을 업데이트하기:

`config.yaml`에서 사용자 이름을 업데이트하려면 `-i` (in-place) 옵션을 사용하여 `yq eval` 명령을 사용하세요:

```bash
yq e '.user.name = "newadmin"' -i config.yaml
```

다음으로 변경 사항을 확인하세요:

```bash
yq e '.user.name' config.yaml
```

**샘플 출력:**

```
newadmin
```

### 새 요소 추가하기:

데이터베이스 섹션 아래에 새 필드 `timeout`처럼 새 요소를 추가하려면:

```bash
yq e '.database.timeout = 30' -i config.yaml
```

파일의 내용을 확인하면 추가가 확인됩니다.

### 요소 삭제하기:

사용자 아래의 비밀번호를 제거하려면:

```bash
yq e 'del(.user.password)' -i config.yaml
```

이 작업은 구성에서 비밀번호 필드를 제거할 것입니다.

기억하세요, `yq`는 매우 강력한 도구이며, YAML을 JSON으로 변환, 파일 병합, 그리고 더 복잡한 조작을 포함하여 많은 기능을 가지고 있습니다. 더 많은 탐구를 위해 `yq` 문서를 참조하세요.
