---
title:                "Interpolating a string"
aliases:
- /en/python/interpolating-a-string/
date:                  2024-01-20T17:51:28.373461-07:00
model:                 gpt-4-1106-preview
simple_title:         "Interpolating a string"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/python/interpolating-a-string.md"
changelog:
  - 2024-01-28, dogweather, reviewed
---

{{< edit_this_page >}}

## What & Why?
String interpolation is the method of embedding expressions within string literals. Programmers use it to dynamically insert values into strings, which makes the code more readable and cleaner than traditional string concatenation.

## How to:
In Python 3.6 and above, you can interpolate strings using f-strings. Here's how:

```Python
name = 'Alice'
age = 30
greeting = f"Hello, {name}. You are {age} years old."

print(greeting)
```

Output:
```
Hello, Alice. You are 30 years old.
```

You can also use expressions inside the curly braces:

```Python
a = 5
b = 10
info = f"Five plus ten is {a + b}, not {2 * (a + b)}."

print(info)
```

Output:
```
Five plus ten is 15, not 30.
```

## Deep Dive
Before Python 3.6, `.format()` was the way to go for interpolating strings:

```Python
name = 'Bob'
age = 25
greeting = "Hello, {}. You are {} years old.".format(name, age)

print(greeting)
```

Old school Python (versions < 2.6) used the `%` operator for interpolation, which is less intuitive and can get messy with multiple variables:

```Python
name = 'Carol'
age = 35
greeting = "Hello, %s. You are %d years old." % (name, age)

print(greeting)
```

Besides cleaner syntax, f-strings are faster because they are evaluated at runtime and then converted directly into an efficient string format operation. The `.format()` and `%` operator involve more steps and are slower.

## See Also
- [PEP 498 – Literal String Interpolation](https://www.python.org/dev/peps/pep-0498/) for official documentation on f-strings.
- [Python f-strings](https://realpython.com/python-f-strings/) by Real Python for a tutorial on using f-strings.
- [The .format() Method](https://docs.python.org/3/library/stdtypes.html#str.format) in the Python documentation to understand the older `.format()` method of string formatting.
