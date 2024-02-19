---
aliases:
- /en/ruby/using-an-interactive-shell-repl/
date: 2024-01-25 03:39:37.470710-07:00
description: "An interactive shell, or REPL (Read-Eval-Print Loop), lets you test\
  \ code in real time. Programmers use it to experiment, debug, and learn Ruby's nuances\u2026"
lastmod: 2024-02-18 23:09:11.567553
model: gpt-4-1106-preview
summary: "An interactive shell, or REPL (Read-Eval-Print Loop), lets you test code\
  \ in real time. Programmers use it to experiment, debug, and learn Ruby's nuances\u2026"
title: Using an interactive shell (REPL)
---

{{< edit_this_page >}}

## What & Why?
An interactive shell, or REPL (Read-Eval-Print Loop), lets you test code in real time. Programmers use it to experiment, debug, and learn Ruby's nuances without creating full-blown scripts.

## How to:
Ruby's REPL is called IRB (Interactive Ruby). Jump in and try Ruby straight from your terminal:

```Ruby
irb
2.7.0 :001 > puts "Hello, Ruby world!"
Hello, Ruby world!
 => nil
2.7.0 :002 > 5.times { print "Ruby! " }
Ruby! Ruby! Ruby! Ruby! Ruby!  => 5
```

## Deep Dive
Introduced in Ruby 1.8, IRB is a staple for Rubyists. It's inspired by the interactive shells of Lisp and Python, melding experimentation with immediate feedback. Alternatives like Pry offer more features like syntax highlighting and a more robust debugging environment. IRB itself is simple but can be augmented with gems like 'irbtools' to extend functionality. How IRB handles the read-eval-print loop is by reading each line of input, evaluating it as Ruby code, and then printing the result, looping this process until exit.

## See Also
- [Ruby's IRB](https://ruby-doc.org/stdlib-2.7.0/libdoc/irb/rdoc/IRB.html)
- [The irbtools gem](https://github.com/janlelis/irbtools)
