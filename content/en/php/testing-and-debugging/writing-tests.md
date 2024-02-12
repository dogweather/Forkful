---
title:                "Writing tests"
aliases:
- en/php/writing-tests.md
date:                  2024-02-03T19:03:31.505464-07:00
model:                 gpt-4-0125-preview
simple_title:         "Writing tests"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/php/writing-tests.md"
---

{{< edit_this_page >}}

## What & Why?
Writing tests in programming involves creating and running scripts that verify the code behaves as expected under various conditions. Programmers do it to ensure quality, prevent regressions, and facilitate safe refactoring, which is crucial for maintaining a healthy, scalable, and bug-free codebase.

## How to:
### Native PHP – PHPUnit
A widely-used tool for testing in PHP is PHPUnit. Install it via Composer:
```bash
composer require --dev phpunit/phpunit ^9
```

#### Writing a simple test:
Create a `CalculatorTest.php` file in a `tests` directory:
```php
use PHPUnit\Framework\TestCase;

// Assuming you have a Calculator class that adds numbers
class CalculatorTest extends TestCase
{
    public function testAdd()
    {
        $calculator = new Calculator();
        $this->assertEquals(4, $calculator->add(2, 2));
    }
}
```
Run the tests with:
```bash
./vendor/bin/phpunit tests
```

#### Sample output:
```
PHPUnit 9.5.10 by Sebastian Bergmann and contributors.

.                                                                   1 / 1 (100%)

Time: 00:00.005, Memory: 6.00 MB

OK (1 test, 1 assertion)
```

### Third-party Libraries – Mockery
For complex testing, including mocking objects, Mockery is a popular choice.

```bash
composer require --dev mockery/mockery
```

#### Integrating Mockery with PHPUnit:
```php
use PHPUnit\Framework\TestCase;
use Mockery as m;

class ServiceTest extends TestCase
{
    public function tearDown(): void
    {
        m::close();
    }

    public function testServiceCallsExternalService()
    {
        $externalServiceMock = m::mock(ExternalService::class);
        $externalServiceMock->shouldReceive('process')->once()->andReturn('mocked result');

        $service = new Service($externalServiceMock);
        $result = $service->execute();

        $this->assertEquals('mocked result', $result);
    }
}
```
To run, use the same PHPUnit command as above. Mockery allows for expressive and flexible mock objects, facilitating testing of complex interactions within your application.
