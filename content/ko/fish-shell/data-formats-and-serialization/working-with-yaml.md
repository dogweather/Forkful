---
title:                "YAML로 작업하기"
date:                  2024-02-03T19:25:28.021229-07:00
model:                 gpt-4-0125-preview
simple_title:         "YAML로 작업하기"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/fish-shell/working-with-yaml.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 무엇 & 왜?
Fish Shell에서 YAML을 다루는 일은 YAML (YAML Ain't Markup Language) 파일, 구성 파일에 사용되는 데이터 직렬화 형식을 파싱하고 조작하는 것을 포함합니다. 프로그래머들은 쉘 환경의 맥락에서 어플리케이션이나 서비스를 자동화하고 구성하는 것을 효율적으로 수행하기 위해 이를 수행합니다. 이는 설정 관리와 자원의 프로비저닝과 같은 작업을 용이하게 합니다.

## 방법:
Fish Shell은 YAML 파싱을 내장 지원하지 않지만, `yq`(가벼우면서 이식 가능한 커맨드라인 YAML 프로세서) 같은 제3자 도구를 사용해 YAML 데이터를 처리할 수 있습니다.

**yq 설치하기(미설치시):**
```fish
sudo apt-get install yq
```

**YAML 파일에서 값 읽기:**
예를 들어, 다음과 같은 내용의 `config.yaml` 파일이 있다고 가정합시다:
```yaml
database:
  host: localhost
  port: 3306
```

데이터베이스 호스트를 읽으려면, 다음을 사용합니다:
```fish
set host (yq e '.database.host' config.yaml)
echo $host
```
**샘플 출력:**
```
localhost
```

**YAML 파일 내 값 업데이트하기:**
`port`를 `5432`로 업데이트 하려면, 사용합니다:
```fish
yq e '.database.port = 5432' -i config.yaml
```
**업데이트 확인:**
```fish
yq e '.database.port' config.yaml
```
**샘플 출력:**
```
5432
```

**새 YAML 파일 작성하기:**
미리 정의된 내용으로 새로운 `new_config.yaml`을 생성하려면:
```fish
echo "webserver:
  host: '127.0.0.1'
  port: 8080" | yq e -P - > new_config.yaml
```
이는 `yq`를 사용하여 문자열을 처리하고 새 YAML 파일로 예쁘게 출력하는(-P 플래그) 것을 사용합니다.

**복잡한 구조 파싱하기:**
더 복잡한 YAML 파일이 있고, 중첩된 배열이나 객체를 추출해야 한다면, 다음을 사용할 수 있습니다:
```fish
echo "servers:
  - name: server1
    ip: 192.168.1.101
  - name: server2
    ip: 192.168.1.102" > servers.yaml

yq e '.servers[].name' servers.yaml
```
**샘플 출력:**
```
server1
server2
```
`yq`를 사용하여, Fish Shell은 YAML 문서를 탐색하고 다양한 자동화 및 구성 작업을 위해 조작하는 것을 간단하게 만들어 줍니다.
