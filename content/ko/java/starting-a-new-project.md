---
title:                "새 프로젝트 시작하기"
date:                  2024-01-20T18:03:43.102396-07:00
model:                 gpt-4-1106-preview
simple_title:         "새 프로젝트 시작하기"
programming_language: "Java"
category:             "Java"
tag:                  "Getting Started"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/java/starting-a-new-project.md"
---

{{< edit_this_page >}}

## What & Why? (무엇과 왜?)
새 프로젝트를 시작한다는 것은 빈 캔버스에 그림을 그리기 시작하는 것과 비슷해요. 프로그래머는 새로운 아이디어를 현실로 만들거나, 기술을 배우고 테스트하기 위해 새 프로젝트를 만듭니다.

## How to (어떻게):
쉽게 말해 Java 프로젝트를 시작하는 건 간단해요. IDE(통합 개발 환경)를 쓰던, 직접 디렉토리를 설정하던, 기본 구조는 비슷합니다. 여기 IntelliJ IDEA를 사용하는 기본 예제를 보여드릴게요.

```java
// Main.java
public class Main {
    public static void main(String[] args) {
        System.out.println("새 프로젝트, 시작!");
    }
}
```

실행 결과:

```java
새 프로젝트, 시작!
```

## Deep Dive (심층 탐구):
과거엔 모든 것을 수동으로 설정해야 했어요. 디렉토리 생성, CLASSPATH 설정, 컴파일 방법 등을 직접 했죠. 지금은 IntelliJ, Eclipse 등의 IDE가 자동으로 처리해줘요. 더 나아가, Maven이나 Gradle 같은 빌드 도구를 사용해 종속성 관리와 빌드 과정을 자동화할 수 있어요.

단순 Java 프로젝트 외에도 스프링 부트나 마이크로 서비스를 위한 프로젝트를 시작하는 경우가 많아요. 이런 프로젝트들은 초기 설정에 더 많은 관심이 필요하지만, spring initializr(https://start.spring.io/) 같은 도구를 쓰면 쉽게 시작할 수 있습니다.

한편, 배운 것을 시험하고 싶을 땐, 코딩 도전 과제나 작은 클론 프로젝트부터 시작하는 것도 좋은 방법입니다.

## See Also (참고 자료):
- Oracle의 Java Tutorial: https://docs.oracle.com/javase/tutorial/
- IntelliJ IDEA 가이드: https://www.jetbrains.com/idea/guide/
- Maven: https://maven.apache.org/
- Gradle: https://gradle.org/
- Spring Initializr: https://start.spring.io/
