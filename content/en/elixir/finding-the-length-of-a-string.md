---
title:                "Finding the length of a string"
date:                  2024-01-20T17:47:09.017824-07:00
model:                 gpt-4-1106-preview
simple_title:         "Finding the length of a string"
programming_language: "Elixir"
category:             "Elixir"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/elixir/finding-the-length-of-a-string.md"
---

{{< edit_this_page >}}

## What & Why?
Finding the length of a string means determining the number of characters it contains. Programmers do it to validate input, enforce limits, or align output.

## How to:
In Elixir, you get a string's length with the `String.length/1` function. Here's how:

```elixir
my_string = "Hello, World!"
length = String.length(my_string)
IO.puts(length)
```

Sample output:

```
13
```

## Deep Dive
Internally, Elixir strings are UTF-8 encoded binaries. Each character can be one to four bytes. So, when we call `String.length/1`, we're not merely counting bytes; we're counting Unicode graphemes, which are what we perceive as characters.

Historically, string length operations in many languages were byte-centric and did not account well for multi-byte characters. Elixir's approach is modern and Unicode-friendly from the get-go.

As for alternatives, you could manually count graphemes using recursion or with a loop, but that's unnecessary and inefficient. `String.length/1` is optimized and idiomatic.

Elixir's implementation uses an Erlang NIF (Native Implemented Function) for `String.length/1`, making it lightning fast. Counting bytes instead of graphemes is done with `byte_size/1`, which counts the raw bytes of a string's binary representation—useful in low-level operations where encoding doesn't matter.

## See Also
- [Elixir's String module documentation](https://hexdocs.pm/elixir/String.html)
- [Unicode Standard](http://www.unicode.org/standard/standard.html)
