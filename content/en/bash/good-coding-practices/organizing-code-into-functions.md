---
title:                "Organizing code into functions"
aliases:
- /en/bash/organizing-code-into-functions/
date:                  2024-01-25T02:59:53.827268-07:00
model:                 gpt-4-1106-preview
simple_title:         "Organizing code into functions"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/bash/organizing-code-into-functions.md"
---

{{< edit_this_page >}}

## What & Why?
Splitting code into functions means breaking down scripts into smaller, reusable blocks that do specific tasks. It makes the code cleaner, more understandable, and easier to debug.

## How to:
Create a simple function in Bash:

```Bash
greet() {
  echo "Hello, $1!"
}
```

Use it by calling the function with a parameter:

```Bash
greet "World"  # Output: Hello, World!
```

Functions can return values using `return` for numeric status codes (not for actual data return):

```Bash
add() {
  return $(($1 + $2))
}

add 3 4
echo $?  # Output: 7
```

Note that `$?` captures the last command's return value, which is the numeric result of `add`.

## Deep Dive
In Bash, functions have been a way to compartmentalize code since the early versions. Historically, using functions aligns with structured programming principles introduced in the 1960s to improve code quality.

Alternatives to functions include sourcing script files or using aliases, but these don't offer the same level of modularity and reuse. 

A notable implementation detail in Bash is that functions are first-class citizens; they have no specific declaration keyword like `function` in other languages, though `function` is optional in Bash for readability. Function scope is also interesting—variables are global by default unless declared as local, which can lead to unexpected behavior if not managed properly.

## See Also
- Bash manual on Shell Functions: https://www.gnu.org/software/bash/manual/html_node/Shell-Functions.html
- Advanced Bash-Scripting Guide: https://tldp.org/LDP/abs/html/functions.html
- "Pro Bash Programming: Scripting the GNU/Linux Shell" for in-depth function scripting concepts and practices.
