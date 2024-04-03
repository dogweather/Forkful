---
date: 2024-01-20 17:38:50.587159-07:00
description: "Changing a string to lower case means making every letter in the string\
  \ a small letter. Programmers do this to standardize text, to make comparisons,\
  \ and\u2026"
lastmod: '2024-03-13T22:45:00.270406-06:00'
model: gpt-4-1106-preview
summary: Changing a string to lower case means making every letter in the string a
  small letter.
title: Converting a string to lower case
weight: 4
---

## How to:
PowerShell is pretty handy with strings. Use the `.ToLower()` method, like this:

```PowerShell
$string = "HELLO, World!"
$lowerCaseString = $string.ToLower()
$lowerCaseString
```

Output:

```
hello, world!
```

Or try the `ToLowerInvariant()` method when cultural norms shouldn’t affect the conversion:

```PowerShell
$string = "HELLO, World!"
$lowerCaseInvariant = $string.ToLowerInvariant()
$lowerCaseInvariant
```

Output:

```
hello, world!
```

## Deep Dive
Once upon a time, case insensitivity was pretty common in programming languages. In PowerShell, like its .NET ancestors, strings are objects with built-in methods for manipulation. When we use `.ToLower()`, we're invoking a method that handles the conversion process for us.

Alternative ways to get the job done? Sure. You could use:

- a `for` loop, visiting each character, and case switching manually
- Regular Expressions with the `-replace` operator
- Culture-specific conversions using overloads of `.ToLower()`
  
Why use the invariant culture with `ToLowerInvariant()`? It's essential for consistent results across different locales where the interpretation of what is a "lower" case could differ.

## See Also
For more detailed adventures in string manipulation, visit these links:

- [.NET String Class](https://docs.microsoft.com/en-us/dotnet/api/system.string?view=net-6.0)
