---
title:                "YAML로 작업하기"
aliases:
- ko/rust/working-with-yaml.md
date:                  2024-02-03T19:26:58.467053-07:00
model:                 gpt-4-0125-preview
simple_title:         "YAML로 작업하기"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/rust/working-with-yaml.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 무엇 & 왜?

Rust 프로그래밍에서 YAML(YAML Ain't Markup Language)을 다루는 것은 YAML 형식으로 데이터를 파싱하고 생성하는 것에 관한 것입니다. YAML 형식은 사람이 읽기 편한 데이터 직렬화 표준입니다. 프로그래머들은 응용 프로그램을 구성하거나, 설정을 관리하거나, 복잡한 데이터 구조를 명확하고 읽기 쉬운 형식으로 처리하기 위해 Rust에서 YAML 처리를 통합합니다. 이는 구성 파일과 데이터 교환을 위해 JSON이나 XML보다 간단함을 활용합니다.

## 방법:

Rust는 표준 라이브러리에서 YAML을 지원하지 않으므로 일반적으로 `serde`(데이터를 직렬화 및 역직렬화하는 데 사용)와 `serde_yaml`을 조합하여 서드 파티 크레이트를 사용합니다.

먼저, `Cargo.toml`에 의존성을 추가하세요.

```toml
[dependencies]
serde = { version = "1.0", features = ["derive"] }
serde_yaml = "0.8"
```

이제, YAML 문자열을 Rust 구조체로 역직렬화하고 Rust 구조체를 다시 YAML 문자열로 직렬화하는 방법을 살펴보겠습니다.

### YAML을 Rust 구조체로 역직렬화하기

당신이 YAML에서 기대하는 데이터를 반영하는 Rust 구조체를 정의하세요. 필요한 경우 Serde 속성을 사용하여 사용자 정의를 할 수 있습니다.

```rust
use serde::{Deserialize, Serialize};
use serde_yaml;

#[derive(Debug, PartialEq, Serialize, Deserialize)]
struct Config {
    name: String,
    durability: i32,
    owner: Owner,
}

#[derive(Debug, PartialEq, Serialize, Deserialize)]
struct Owner {
    name: String,
    age: i32,
}

fn main() {
    let yaml_data = "
name: Shield
durability: 300
owner:
  name: Steve
  age: 25
";

    let deserialized_config: Config = serde_yaml::from_str(yaml_data).unwrap();
    println!("{:?}", deserialized_config);
}
```

위 Rust 코드를 실행하면 다음과 같은 샘플 출력이 나옵니다:

```plaintext
Config { name: "Shield", durability: 300, owner: Owner { name: "Steve", age: 25 } }
```

### Rust 구조체를 YAML로 직렬화하기

이 예제는 이전 섹션의 `Config` 구조체를 다시 YAML 형식으로 직렬화합니다.

```rust
fn main() {
    let config = Config {
        name: String::from("Axe"),
        durability: 120,
        owner: Owner {
            name: String::from("Alex"),
            age: 30,
        },
    };

    let serialized_yaml = serde_yaml::to_string(&config).unwrap();
    println!("{}", serialized_yaml);
}
```

예상 출력은 YAML 형식 문자열일 것입니다:

```yaml
---
name: Axe
durability: 120
owner:
  name: Alex
  age: 30
```

이 코드 조각들은 Rust 응용 프로그램에서 YAML 파싱 및 생성을 효율적으로 통합하는 방법을 보여줍니다. 이는 인기 있는 `serde` 및 `serde_yaml` 크레이트를 사용하여 복잡한 데이터 구조에 대응하고 간단하며 사람이 읽을 수 있는 구성을 제공합니다.
