---
aliases:
- /es/elixir/using-an-interactive-shell-repl/
date: 2024-01-26 04:13:02.044311-07:00
description: "Una shell interactiva, o REPL (Read-Eval-Print Loop, Bucle de Leer-Evaluar-Imprimir),\
  \ te permite probar fragmentos de c\xF3digo en tiempo real. Los\u2026"
lastmod: 2024-02-18 23:09:09.650356
model: gpt-4-0125-preview
summary: "Una shell interactiva, o REPL (Read-Eval-Print Loop, Bucle de Leer-Evaluar-Imprimir),\
  \ te permite probar fragmentos de c\xF3digo en tiempo real. Los\u2026"
title: Usando una shell interactiva (REPL)
---

{{< edit_this_page >}}

## Qué y Por Qué?
Una shell interactiva, o REPL (Read-Eval-Print Loop, Bucle de Leer-Evaluar-Imprimir), te permite probar fragmentos de código en tiempo real. Los programadores de Elixir usan la REPL, llamada IEx (Elixir Interactivo), para experimentar, depurar y aprender el lenguaje.

## Cómo hacerlo:
Para lanzar IEx, abre tu terminal y escribe `iex`. Aquí tienes un adelanto:

```Elixir
iex> nombre = "Programador de Elixir"
"Programador de Elixir"
iex> String.length(nombre)
17
iex> Enum.map([1, 2, 3], fn num -> num * 3 end)
[3, 6, 9]
```

La salida debería mostrar la asignación de variables, resultados de funciones y una función anónima en acción.

## Profundización
La shell IEx ha sido parte de Elixir desde sus primeros días. José Valim, el creador de Elixir, se inspiró en las shells interactivas de otros lenguajes como el `python` de Python y el `irb` de Ruby. Aunque IEx comparte muchas características con estos, está diseñado para manejar la naturaleza concurrente de Elixir y está completamente integrado con las capacidades de la VM de Erlang.

Las alternativas a IEx en el ecosistema de Erlang incluyen `erl`, la shell de Erlang. Pero IEx ofrece un entorno más amigable para Elixir, con características como completación de tabulador comprehensiva, historial y ayudantes.

La REPL IEx es más que un área de juegos; puede conectarse sin problemas a un sistema en ejecución. Esto es crucial para depurar aplicaciones en vivo. La implementación subyacente se basa en el BEAM (la VM de Erlang), asegurando que características como el intercambio de código en caliente estén soportadas directamente en la shell.

## Ver También
Consulta estos para más lectura y recursos:

- [Documentación de IEx de Elixir](https://hexdocs.pm/iex/IEx.html)
- [Elixir Interactivo (IEx) - La Shell de Elixir](https://elixir-lang.org/getting-started/introduction.html#interactive-elixir)
- [Documentación de `erl` de Erlang](http://erlang.org/doc/man/erl.html)
- [Aprendiendo la Shell Interactiva de Elixir](https://elixirschool.com/en/lessons/basics/iex_helpers/)
