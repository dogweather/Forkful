---
changelog:
- 2024-01-29, gpt-4-0125-preview, translated from English
date: 2024-01-29 00:06:02.594220-07:00
description: "\u0422\u0435\u0441\u0442\u0438\u0440\u043E\u0432\u0430\u043D\u0438\u0435\
  \ \u043F\u0440\u043E\u0432\u0435\u0440\u044F\u0435\u0442, \u0432\u044B\u043F\u043E\
  \u043B\u043D\u044F\u0435\u0442 \u043B\u0438 \u0432\u0430\u0448 \u043A\u043E\u0434\
  \ \u0442\u043E, \u0447\u0442\u043E \u043E\u0442 \u043D\u0435\u0433\u043E \u0442\u0440\
  \u0435\u0431\u0443\u0435\u0442\u0441\u044F. \u042D\u0442\u043E \u044D\u043A\u043E\
  \u043D\u043E\u043C\u0438\u0442 \u0432\u0440\u0435\u043C\u044F, \u0432\u044B\u044F\
  \u0432\u043B\u044F\u044F \u043E\u0448\u0438\u0431\u043A\u0438 \u043D\u0430 \u0440\
  \u0430\u043D\u043D\u0435\u043C \u044D\u0442\u0430\u043F\u0435, \u0438 \u0433\u0430\
  \u0440\u0430\u043D\u0442\u0438\u0440\u0443\u0435\u0442, \u0447\u0442\u043E \u0438\
  \u0437\u043C\u0435\u043D\u0435\u043D\u0438\u044F \u0432\u2026"
lastmod: '2024-03-13T22:44:45.217145-06:00'
model: gpt-4-0125-preview
summary: "\u0422\u0435\u0441\u0442\u0438\u0440\u043E\u0432\u0430\u043D\u0438\u0435\
  \ \u043F\u0440\u043E\u0432\u0435\u0440\u044F\u0435\u0442, \u0432\u044B\u043F\u043E\
  \u043B\u043D\u044F\u0435\u0442 \u043B\u0438 \u0432\u0430\u0448 \u043A\u043E\u0434\
  \ \u0442\u043E, \u0447\u0442\u043E \u043E\u0442 \u043D\u0435\u0433\u043E \u0442\u0440\
  \u0435\u0431\u0443\u0435\u0442\u0441\u044F."
title: "\u041D\u0430\u043F\u0438\u0441\u0430\u043D\u0438\u0435 \u0442\u0435\u0441\u0442\
  \u043E\u0432"
weight: 36
---

## Как это сделать:
Мы рассмотрим PHPUnit, популярную рамочную программу тестирования для PHP. Сначала установите его с помощью Composer:

```bash
composer require --dev phpunit/phpunit
```

Теперь давайте напишем простой тест. Представьте, что у вас есть класс `Calculator` с методом `add`.

```php
// Calculator.php
class Calculator {
    public function add($a, $b) {
        return $a + $b;
    }
}
```

Вот как вы можете его протестировать:

```php
// CalculatorTest.php
use PHPUnit\Framework\TestCase;

class CalculatorTest extends TestCase {
    public function testAddition() {
        $calculator = new Calculator();
        $this->assertEquals(4, $calculator->add(2, 2));
    }
}
```

Запустите тест с помощью:

```bash
./vendor/bin/phpunit CalculatorTest
```

Вывод покажет, пройдены тесты или нет.

## Погружение в тему
Тестирование не всегда было важной частью раработки в PHP. Изначально многие просто сочиняли код и вручную проверяли его работоспособность. Теперь тестирование - это закон. PHPUnit начал набирать популярность в 2000-х, и теперь это практически стандарт. Альтернативы? Конечно, есть PHPSpec и Behat для начала. Под капотом PHPUnit использует утверждения для сравнения ожидаемых и фактических результатов и тестовые двойники (моки, стабы, шпионы) для имитации внешних зависимостей.

## Смотрите также
- Руководство по PHPUnit: https://phpunit.de/manual/current/en/index.html
- PHP Правильный путь (Тестирование): http://www.phptherightway.com/#testing
- Mockery (фреймворк мокирования для PHPUnit): http://docs.mockery.io/en/latest/
