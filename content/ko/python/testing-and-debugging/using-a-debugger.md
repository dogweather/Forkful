---
date: 2024-01-26 04:09:15.778524-07:00
description: "\"\uB514\uBC84\uAC70 \uC0AC\uC6A9\uD558\uAE30\"\uB294 Python \uCF54\uB4DC\
  \uB97C \uB2E8\uACC4\uBCC4\uB85C \uC9C4\uD589\uD558\uBA70 \uBC84\uADF8\uB97C \uCC3E\
  \uACE0 \uD589\uB3D9\uC744 \uC774\uD574\uD558\uB294 \uACFC\uC815\uC785\uB2C8\uB2E4\
  . \uCD94\uCE21\uB9CC \uD558\uBA70 \uC5B4\uB514\uC11C \uBB38\uC81C\uAC00 \uBC1C\uC0DD\
  \uD588\uB294\uC9C0 \uCC3E\uB294 \uAC83\uBCF4\uB2E4 \uD6E8\uC52C \uC26C\uC6B0\uBA70\
  , \uC774\uB294 \uC6B0\uB9AC\uC5D0\uAC8C \uC218\uC2DC\uAC04\uC758 print \uBB38 \uC9C0\
  \uC625\uC5D0\uC11C \uBC97\uC5B4\uB098\uAC8C \uD574 \uC90D\uB2C8\uB2E4."
lastmod: '2024-03-13T22:44:54.604474-06:00'
model: gpt-4-0125-preview
summary: "\"\uB514\uBC84\uAC70 \uC0AC\uC6A9\uD558\uAE30\"\uB294 Python \uCF54\uB4DC\
  \uB97C \uB2E8\uACC4\uBCC4\uB85C \uC9C4\uD589\uD558\uBA70 \uBC84\uADF8\uB97C \uCC3E\
  \uACE0 \uD589\uB3D9\uC744 \uC774\uD574\uD558\uB294 \uACFC\uC815\uC785\uB2C8\uB2E4\
  . \uCD94\uCE21\uB9CC \uD558\uBA70 \uC5B4\uB514\uC11C \uBB38\uC81C\uAC00 \uBC1C\uC0DD\
  \uD588\uB294\uC9C0 \uCC3E\uB294 \uAC83\uBCF4\uB2E4 \uD6E8\uC52C \uC26C\uC6B0\uBA70\
  , \uC774\uB294 \uC6B0\uB9AC\uC5D0\uAC8C \uC218\uC2DC\uAC04\uC758 print \uBB38 \uC9C0\
  \uC625\uC5D0\uC11C \uBC97\uC5B4\uB098\uAC8C \uD574 \uC90D\uB2C8\uB2E4."
title: "\uB514\uBC84\uAC70 \uC0AC\uC6A9\uD558\uAE30"
---

## 방법:
Python의 내장 디버거인 `pdb` 사용을 살펴봅시다. `buggy.py`라는 파일에 까다로운 버그가 있는 상황을 상상해 봅시다:

```Python
def add_one(number):
    result = number ++ 1
    return result

print(add_one(7))
```

이 스크립트를 실행하면 `8`이 나올 것으로 기대하지만, 문법 오류가 발생합니다. 이제 디버거 사용할 시간입니다!

터미널에서 다음을 실행하세요:
```bash
python -m pdb buggy.py
```

디버거에 진입하면 다음과 같은 화면이 보입니다:
```Python
> /path_to_file/buggy.py(1)<module>()
-> def add_one(number):
```

`l(ist)`를 사용해서 더 많은 코드를 보기, `n(ext)`를 사용해서 다음 줄로 가기, 또는 `c(ontinue)`를 사용해서 스크립트를 계속 실행하기 등을 할 수 있습니다. 오류를 만나면, `pdb`가 멈추고 검사할 수 있게 해줍니다.

`number ++ 1`을 `number + 1`로 바로잡은 후에 디버거를 다시 시작해서 수정사항을 테스트하세요.
기억하세요, 친구는 친구를 그물 없이 코드를 작성하게 내버려두지 않습니다. 이상입니다.

## 심층 탐구
프로그래밍의 암흑기(즉, 통합 개발 환경, 또는 IDE가 어디에나 있기 전)에는, 디버거는 종종 텍스트 편집기 외부에서 사용하는 독립 실행형 도구였습니다. 프로그래머가 소프트웨어의 상태를 다양한 실행 지점에서 검사할 수 있게 해주어 구조를 제공했습니다.

2023년 현재, Python의 `pdb`는 유일한 선택지가 아닙니다. PyCharm이나 Visual Studio Code 같은 IDE를 사용하는 사람들이 있으며, 이들은 자체적인 슬릭한 디버거를 내장하고 있습니다. 이들은 암호화된 명령어를 입력하는 대신 클릭으로 설정할 수 있는 브레이크포인트와 같은 편리한 기능을 추가합니다.

그리고 `ipdb`가 있는데, 이는 `IPython`의 장점을 디버깅에 가져오는 pip로 설치할 수 있는 패키지입니다. 탭 완성과 구문 하이라이팅과 함께, `pdb`에 성능 향상 요소를 더한 것과 같습니다.

디버거는 구현에 있어서도 다양합니다. 일부는 머신 또는 바이트 코드 수준에서 프로그램 실행과 밀접하게 관련되어 있습니다. 다른 것들, 많은 고급 언어 디버거들처럼, 변수 상태를 모니터링하고 실행 흐름을 제어하는 특별한 환경에서 코드를 실행합니다.

## 참고 자료
Python 자체 디버거에 대한 전체 내용을 확인하십시오:
- `pdb` 문서: https://docs.python.org/3/library/pdb.html

대안에 대해 궁금하다면, 이 링크들이 도움이 될 것입니다:
- `ipdb` 리포지토리 및 사용 안내서: https://github.com/gotcha/ipdb
- Visual Studio Code를 사용한 디버깅: https://code.visualstudio.com/docs/python/debugging
- PyCharm 디버깅 기능: https://www.jetbrains.com/help/pycharm/debugging-code.html

버그 사냥에 행운을 빕니다!
