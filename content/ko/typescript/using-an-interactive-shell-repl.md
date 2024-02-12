---
title:                "인터랙티브 셸 (REPL) 사용하기"
aliases:
- ko/typescript/using-an-interactive-shell-repl.md
date:                  2024-01-26T04:18:45.343946-07:00
model:                 gpt-4-0125-preview
simple_title:         "인터랙티브 셸 (REPL) 사용하기"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/typescript/using-an-interactive-shell-repl.md"
---

{{< edit_this_page >}}

## 무엇인가 & 왜 사용하는가?
Read-Eval-Print-Loop (REPL)은 사용자 입력을 받아 실행한 후 결과를 사용자에게 반환하는 프로그래밍 환경입니다. 프로그래머들은 REPL을 사용하여 코드 스니펫을 빠르게 실험하고, 디버깅하며, 전체 애플리케이션을 만들지 않고도 새로운 언어 기능을 배우기 위해 사용합니다.

## 사용 방법:
TypeScript는 자체 REPL을 포함하고 있지 않습니다. Node.js용 TypeScript 실행 환경인 `ts-node`, REPL을 포함하고 있는 `ts-node`를 사용합시다.

먼저, 전역적으로 설치하세요:
```bash
npm install -g ts-node
```

명령 줄에 `ts-node`를 입력하여 REPL을 시작하세요:
```bash
ts-node
```

시도해 볼 간단한 스니펫입니다:
```TypeScript
> let message: string = 'Hello, REPL!';
> console.log(message);
Hello, REPL!
> 
```
세션을 종료하려면 `Ctrl+D`를 누르세요.

## 심층 탐구
역사적으로, REPL은 Lisp과 같은 언어에서 동적 코드 평가를 위해 두드러졌습니다. 이 개념은 이후로 확산되어, 많은 언어에서 인터랙티브한 코딩을 위한 필수 요소가 되었습니다.

TypeScript에서 `ts-node`는 유일한 옵션이 아닙니다. 대안에는 웹 브라우저에서 TypeScript Playground를 사용하거나, 적합한 플러그인이 지원하는 타사 Node.js 기반 REPL을 사용하는 것이 포함됩니다.

구현면에서, `ts-node`는 Node.js에서 실행되기 전에 TypeScript 컴파일러 API를 사용하여 코드를 즉석에서 트랜스파일합니다. 이는 즉각적인 피드백을 제공하며, 설정의 번거로움 없이 TypeScript의 최신 기능을 시도해보기에 특히 유용합니다.

기억해야 할 한 가지는 – REPL이 빠른 테스트에는 좋지만, 전통적이고 테스트 가능하며 유지 보수가 가능한 코드 작성을 대체하지는 않는다는 것입니다. 이는 학습과 탐색을 위한 도구일 뿐, 적절한 개발 관행의 대체재가 아닙니다.

## 참조
- [TypeScript 공식 웹사이트](https://www.typescriptlang.org/)
- [GitHub의 ts-node](https://github.com/TypeStrong/ts-node)
- [Node.js REPL 문서](https://nodejs.org/api/repl.html)
- [TypeScript Playground](https://www.typescriptlang.org/play)
