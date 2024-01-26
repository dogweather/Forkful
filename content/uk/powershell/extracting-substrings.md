---
title:                "Виділення підрядків"
date:                  2024-01-20T17:46:13.011251-07:00
model:                 gpt-4-1106-preview
simple_title:         "Виділення підрядків"
programming_language: "PowerShell"
category:             "PowerShell"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/powershell/extracting-substrings.md"
---

{{< edit_this_page >}}

## What & Why? (Що і Чому?)
Extracting substrings means pulling out specific parts of a string based on position or pattern. Programmers do it to process or manipulate text—say, to grab a username from an email address or to pull out data from a string.

## How to: (Як це зробити:)
Let's slice and dice strings with PowerShell:

```PowerShell
# Basic substring extraction using a start index and length
$text = "PowerShell rocks"
$substring = $text.Substring(0, 11)
$substring # Outputs: PowerShell

# Using the Split method to extract a substring between delimiters
$email = "user@example.com"
$username = $email.Split("@")[0]
$username # Outputs: user

# Using regex to capture and extract a pattern
$logEntry = "Error:1001:Something went wrong..."
$pattern = "Error:(\d+):"
$errorCode = ([regex]::Match($logEntry, $pattern)).Groups[1].Value
$errorCode # Outputs: 1001
```

## Deep Dive (Поглиблений аналіз)
Substring extraction is a staple in text manipulation, existing since early programming languages. PowerShell offers methods like `.Substring()` and `.Split()` alongside powerful regex (regular expressions) capabilities for pattern-based extraction.

Alternatives? In bash, you might use `cut`, `awk`, or `sed`. In Python, slicing syntax or regex with the `re` module come in handy. But we're about PowerShell's immediate, no-nonsense approach.

In PowerShell, understanding zero-based indexing (where the first character is at position 0) is crucial for `.Substring()`. With regex, it's about patterns, captured in groups—a concept as old as Perl but just as sharp in PowerShell.

## See Also (Додатково)
- For a regex deep dive, check out [Regular-Expressions.info](https://www.regular-expressions.info/powershell.html).
- PowerShell's about_Split [help topic](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_split?view=powershell-7.1).
