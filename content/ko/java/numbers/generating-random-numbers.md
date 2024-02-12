---
title:                "난수 생성"
date:                  2024-01-27T20:34:44.763011-07:00
model:                 gpt-4-0125-preview
simple_title:         "난수 생성"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ko/java/generating-random-numbers.md"
---

{{< edit_this_page >}}

## 무엇 & 왜?

랜덤 숫자 생성은 예측할 수 없는 순서나 정의된 범위 내의 단일 값을 생산하는 것에 관한 것입니다. 프로그래머들은 시뮬레이션, 게임, 보안 응용 프로그램 및 다양한 조건에서 알고리즘을 테스트하기 위한 샘플링 방법을 포함하여 다양한 이유로 이 기법을 사용합니다.

## 방법:

자바에서는 `java.util` 패키지의 `Random` 클래스 또는 특정 사용 사례에 대한 `ThreadLocalRandom`과 `SecureRandom` 클래스를 사용하여 랜덤 숫자를 생성할 수 있습니다. 다음 예제는 이러한 클래스의 사용 방법을 설명합니다.

### `Random` 클래스 사용하기
`Random` 클래스는 간단한 의사 랜덤 숫자를 생성하는 방법을 제공합니다.

```Java
import java.util.Random;

public class RandomExample {
    public static void main(String[] args) {
        Random rand = new Random(); // Random 객체 생성

        int randInt = rand.nextInt(50); // 0부터 49까지의 랜덤 정수 생성
        double randDouble = rand.nextDouble(); // 0.0과 1.0 사이의 랜덤 더블 생성
        boolean randBoolean = rand.nextBoolean(); // 랜덤 부울 생성
        
        System.out.println("랜덤 Int: " + randInt);
        System.out.println("랜덤 Double: " + randDouble);
        System.out.println("랜덤 Boolean: " + randBoolean);
    }
}
```

### `ThreadLocalRandom` 클래스 사용하기
동시성 애플리케이션의 경우, `ThreadLocalRandom`은 `Random`보다 효율적입니다.

```Java
import java.util.concurrent.ThreadLocalRandom;

public class ThreadLocalRandomExample {
    public static void main(String[] args) {
        int randInt = ThreadLocalRandom.current().nextInt(1, 101); // 1부터 100까지
        double randDouble = ThreadLocalRandom.current().nextDouble(1.0, 10.0); // 1.0부터 10.0까지
        
        System.out.println("랜덤 Int: " + randInt);
        System.out.println("랜덤 Double: " + randDouble);
    }
}
```

### `SecureRandom` 클래스 사용하기
암호화 작업을 위해서, `SecureRandom`은 더 높은 수준의 보안을 제공합니다.

```Java
import java.security.SecureRandom;

public class SecureRandomExample {
    public static void main(String[] args) {
        SecureRandom secRand = new SecureRandom();
        
        byte[] bytes = new byte[20];
        secRand.nextBytes(bytes); // 바이트를 안전한 랜덤 숫자로 채움
        
        System.out.println("안전한 랜덤 바이트:");
        for (byte b : bytes) {
            System.out.printf("%02x ", b);
        }
    }
}
```

## 심층 탐구

랜덤 번호 생성은 컴퓨팅 초기 이래로 상당히 발전해 왔습니다. 자바의 `Random` 클래스는 선형 합동 공식을 사용하여 의사 랜덤 숫자를 생성하는데, 이는 결정론적이며 높은 보안 응용 프로그램에는 적합하지 않습니다. 이로 인해 더 정교한 알고리즘(예: SHA1PRNG)을 사용하여 암호학적으로 강력한 랜덤 숫자를 생성하는 `SecureRandom`이 도입되었습니다.

그러나 `Random`과 `SecureRandom`은 멀티쓰레드 환경에서의 성능 저하와 같은 단점이 있습니다. 자바 7에서는 이 문제를 해결하기 위해 스레드 로컬 랜덤 숫자 생성기를 제공하는 `ThreadLocalRandom` 클래스가 도입되어 동시성 애플리케이션에서 성능이 크게 향상되었습니다.

이러한 클래스는 대부분의 필요를 충족시키지만, 극도로 높은 규모의 요구 사항이나 특수한 요구 사항의 경우, 개발자는 추가 라이브러리를 탐색하거나 맞춤형 솔루션을 개발할 수 있습니다. 사용 사례의 보안 요구 사항과 성능 요구 사항에 따라 올바른 접근 방법을 선택하는 것이 필수적입니다.
