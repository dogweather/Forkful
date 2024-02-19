---
aliases:
- /pt/php/writing-tests/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:31:17.213264-07:00
description: "Escrever testes em programa\xE7\xE3o envolve criar e executar scripts\
  \ que verificam se o c\xF3digo se comporta conforme esperado sob v\xE1rias condi\xE7\
  \xF5es. Os\u2026"
lastmod: 2024-02-18 23:08:58.244409
model: gpt-4-0125-preview
summary: "Escrever testes em programa\xE7\xE3o envolve criar e executar scripts que\
  \ verificam se o c\xF3digo se comporta conforme esperado sob v\xE1rias condi\xE7\
  \xF5es. Os\u2026"
title: Escrevendo testes
---

{{< edit_this_page >}}

## O Que & Por Que?
Escrever testes em programação envolve criar e executar scripts que verificam se o código se comporta conforme esperado sob várias condições. Os programadores fazem isso para garantir a qualidade, prevenir regressões e facilitar a refatoração segura, o que é crucial para manter uma base de código saudável, escalável e livre de bugs.

## Como fazer:
### PHP Nativo – PHPUnit
Uma ferramenta amplamente utilizada para testes em PHP é o PHPUnit. Instale-a via Composer:
```bash
composer require --dev phpunit/phpunit ^9
```

#### Escrevendo um teste simples:
Crie um arquivo `CalculatorTest.php` em um diretório `tests`:
```php
use PHPUnit\Framework\TestCase;

// Supondo que você tenha uma classe Calculator que adiciona números
class CalculatorTest extends TestCase
{
    public function testAdd()
    {
        $calculator = new Calculator();
        $this->assertEquals(4, $calculator->add(2, 2));
    }
}
```
Execute os testes com:
```bash
./vendor/bin/phpunit tests
```

#### Saída de exemplo:
```
PHPUnit 9.5.10 por Sebastian Bergmann e contribuidores.

.                                                                   1 / 1 (100%)

Tempo: 00:00.005, Memória: 6.00 MB

OK (1 teste, 1 afirmação)
```

### Bibliotecas de Terceiros – Mockery
Para testes complexos, incluindo a simulação de objetos, Mockery é uma escolha popular.

```bash
composer require --dev mockery/mockery
```

#### Integrando o Mockery com PHPUnit:
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
        $externalServiceMock->shouldReceive('process')->once()->andReturn('resultado simulado');

        $service = new Service($externalServiceMock);
        $resultado = $service->execute();

        $this->assertEquals('resultado simulado', $resultado);
    }
}
```
Para executar, use o mesmo comando do PHPUnit acima. O Mockery permite objetos simulados expressivos e flexíveis, facilitando o teste de interações complexas dentro da sua aplicação.
