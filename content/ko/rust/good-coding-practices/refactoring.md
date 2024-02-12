---
title:                "리팩토링"
aliases:
- ko/rust/refactoring.md
date:                  2024-01-26T03:37:03.142882-07:00
model:                 gpt-4-0125-preview
simple_title:         "리팩토링"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/rust/refactoring.md"
---

{{< edit_this_page >}}

## 무엇 & 왜?

리팩토링은 기존 컴퓨터 코드를 재구조화하는 과정입니다—팩터링을 변경—외부 동작을 변경하지 않으면서요. 프로그래머들은 소프트웨어의 비기능적 속성을 개선하기 위해 이 작업을 수행합니다. 예를 들면, 가독성 향상, 복잡성 감소, 유지보수 용이성 개선 및 확장성을 개선하기 위해 내부 아키텍처나 객체 모델을 더 표현적으로 만드는 것입니다.

## 방법:

Rust 코드의 간단한 부분을 더 관용적이고 유지보수가 용이하도록 리팩토링해 봅시다. 정수 벡터의 합을 계산하는 함수부터 시작합니다:

```rust
fn sum(vec: &Vec<i32>) -> i32 {
    let mut sum = 0;
    for i in vec {
        sum += i;
    }
    sum
}

fn main() {
    let numbers = vec![1, 2, 3, 4, 5];
    println!("The sum is {}", sum(&numbers));
}
```

출력:
```
The sum is 15
```

이제 이것을 반복자와 `fold` 메서드를 활용하여 더 관용적인 Rust를 사용하도록 리팩토링해 봅시다:

```rust
fn sum(vec: &[i32]) -> i32 {
    vec.iter().fold(0, |acc, &x| acc + x)
}

fn main() {
    let numbers = vec![1, 2, 3, 4, 5];
    println!("The sum is {}", sum(&numbers));
}
```

출력 변경 없음—여전히 `15`입니다—하지만 리팩토링된 버전은 더 깔끔하고 Rust의 장점인 borrowing과 반복자 메서드를 사용합니다.

## 심층 분석

리팩토링은 Smalltalk 커뮤니티에서 그 뿌리를 두고 있으며, 마틴 파울러의 책 "Refactoring: Improving the Design of Existing Code"에 의해 자바 세계에서 대중화되었습니다. 그 원칙은 보편적이며 안전성과 동시성이 중요한 Rust에도 적용됩니다. Rust는 컴파일 시간에 문제를 포착하여 견고한 코드 작성을 장려하므로, 리팩토링하는 동안 Rust 컴파일러는 안전망 역할을 합니다.

수동 리팩토링 대안에는 코드 포맷팅을 위한 'rustfmt'나 코드 리팩토링 제안을 할 수 있는 린팅 툴 'clippy'와 같은 자동화 도구 사용이 포함됩니다. 그러나 깊은 리팩토링은 이러한 도구로는 완전히 자동화할 수 없는 코드 디자인에 대한 심도있는 이해를 필요로 합니다.

Rust에서 리팩토링은 타입 사용 개선, 라이프타임을 효과적으로 활용하기, 불필요한 할당 줄이기, 필요할 때 `Arc<Mutex<T>>`와 같은 동시성 패턴 사용하기 등을 중심으로 이루어질 수 있습니다. 또한 `unwrap()`에서 `Result<T, E>`로 더 표현적인 에러 처리로 전환하는 것도 흔합니다.

## 참조

Rust에서의 리팩토링을 더 깊게 다루려면:

- 러스트 책: https://doc.rust-lang.org/book/
- 예제로 배우는 Rust: https://doc.rust-lang.org/rust-by-example/
- Clippy, Rust 린팅 툴: https://github.com/rust-lang/rust-clippy
- "Refactoring: Improving the Design of Existing Code" by Martin Fowler: https://martinfowler.com/books/refactoring.html
