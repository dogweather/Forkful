---
title:                "Testien kirjoittaminen"
aliases:
- /fi/php/writing-tests/
date:                  2024-02-03T19:31:22.157866-07:00
model:                 gpt-4-0125-preview
simple_title:         "Testien kirjoittaminen"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/php/writing-tests.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Mikä & Miksi?
Testien kirjoittaminen ohjelmoinnissa tarkoittaa skriptien luomista ja suorittamista, jotka varmistavat koodin toimivan odotetusti eri olosuhteissa. Ohjelmoijat tekevät sen laadun varmistamiseksi, regressioiden estämiseksi ja turvallisen refaktoroinnin mahdollistamiseksi, mikä on ratkaisevan tärkeää terveellisen, skaalautuvan ja bugittoman koodikannan ylläpitämiseksi.

## Kuinka:
### Natiivi PHP – PHPUnit
Laajalti käytetty työkalu PHP:n testaamiseen on PHPUnit. Asenna se Composerin kautta:
```bash
composer require --dev phpunit/phpunit ^9
```

#### Yksinkertaisen testin kirjoittaminen:
Luo `CalculatorTest.php` -tiedosto `tests` -hakemistoon:
```php
use PHPUnit\Framework\TestCase;

// Olettaen, että sinulla on Calculator-luokka, joka lisää numeroita
class CalculatorTest extends TestCase
{
    public function testAdd()
    {
        $calculator = new Calculator();
        $this->assertEquals(4, $calculator->add(2, 2));
    }
}
```
Suorita testit komennolla:
```bash
./vendor/bin/phpunit tests
```

#### Näyte tulosteesta:
```
PHPUnit 9.5.10 by Sebastian Bergmann and contributors.

.                                                                   1 / 1 (100%)

Aika: 00:00.005, Muisti: 6.00 MB

OK (1 testi, 1 väite)
```

### Kolmannen osapuolen kirjastot – Mockery
Monimutkaiseen testaukseen, mukaan lukien objektien pilkkaaminen, Mockery on suosittu valinta.

```bash
composer require --dev mockery/mockery
```

#### Mockeryn integrointi PHPUnitiin:
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
Suorittaaksesi käytä samaa PHPUnit-komentoa kuin yllä. Mockery mahdollistaa ilmaisuvoimaiset ja joustavat pilkkausobjektit, helpottaen monimutkaisten vuorovaikutusten testaamista sovelluksessasi.
