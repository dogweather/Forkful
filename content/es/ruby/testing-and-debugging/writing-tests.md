---
title:                "Escribiendo pruebas"
aliases:
- /es/ruby/writing-tests/
date:                  2024-02-03T19:31:46.905956-07:00
model:                 gpt-4-0125-preview
simple_title:         "Escribiendo pruebas"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/ruby/writing-tests.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## ¿Qué y por qué?
Probar en Ruby es verificar que tu código se comporte como se espera bajo varias condiciones. Los programistas escriben pruebas para asegurar la corrección, prevenir regresiones y facilitar la refactorización, apuntando a aplicaciones robustas y mantenibles.

## Cómo hacerlo:
Ruby viene con una biblioteca integrada llamada `Test::Unit` para escribir pruebas unitarias, encapsulando prácticas de prueba dentro de estructuras sencillas. Sin embargo, la comunidad de Ruby a menudo se inclina hacia bibliotecas de terceros como RSpec y Minitest debido a su expresividad mejorada y flexibilidad.

### Usando `Test::Unit`:
```ruby
require 'test/unit'

class CalculatorTest < Test::Unit::TestCase
  def test_addition
    result = 2 + 2
    assert_equal 4, result
  end
end
```
Ejecuta tu archivo de prueba desde el terminal, y deberías obtener una salida indicando el éxito o fallo de las pruebas:
```
Loaded suite test_calculator
Started
.
Finished in 0.001288 seconds.
1 tests, 1 assertions, 0 failures, 0 errors, 0 pendings, 0 omissions, 0 notifications
100% passed
```

### Usando RSpec:
RSpec es un marco popular de BDD (Desarrollo Guiado por Comportamiento) para Ruby. Instala la gema con `gem install rspec`, luego inicialízalo en tu proyecto con `rspec --init`.

```ruby
# calculator_spec.rb
require_relative '../calculator'

describe Calculator do
  it 'suma correctamente dos números' do
    expect(Calculator.add(2, 2)).to eq(4)
  end
end
```
Ejecuta las pruebas con el comando `rspec`. Ejemplo de salida:
```
.

Finished in 0.002 seconds (files took 0.1 seconds to load)
1 example, 0 failures
```

### Usando Minitest:
Minitest proporciona un conjunto completo de facilidades para pruebas que soportan TDD, BDD, mocking y benchmarking. Instálalo con `gem install minitest` y úsalo de la siguiente manera:

```ruby
# test_calculator.rb
require 'minitest/autorun'
require_relative '../calculator'

class CalculatorTest < Minitest::Test
  def test_addition
    assert_equal 4, Calculator.add(2, 2)
  end
end
```

Ejecuta tu archivo de prueba directamente o a través de la tarea `rake` configurada para minitest. Ejemplo de salida:
```
Run options: --seed 33407

# Running:

.

Finished in 0.001027s, 974.5922 runs/s, 974.5922 assertions/s.
1 runs, 1 assertions, 0 failures, 0 errors, 0 skips
```

Al implementar pruebas en tus proyectos de Ruby usando estas bibliotecas, te adhieres a las mejores prácticas, lo que lleva a bases de código más confiables y mantenibles.
