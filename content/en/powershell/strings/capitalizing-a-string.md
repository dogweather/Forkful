---
title:                "Capitalizing a string"
date:                  2024-02-03T19:02:42.618463-07:00
model:                 gpt-4-0125-preview
simple_title:         "Capitalizing a string"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/powershell/capitalizing-a-string.md"
---

{{< edit_this_page >}}

## What & Why?
Capitalizing a string in PowerShell involves transforming the first character of a given string to uppercase while leaving the rest of the string unchanged. Programmers often perform this task for formatting purposes, such as preparing text for display in user interfaces or following grammatical rules in generated documents.

## How to:
PowerShell, being a versatile tool, allows you to capitalize a string using straightforward methods without needing third-party libraries. Here's how you can do it:

```powershell
# Using the built-in .Net method 'ToTitleCase' from CultureInfo
$text = "hello world"
$culture = [System.Globalization.CultureInfo]::InvariantCulture
$capitalizedText = $culture.TextInfo.ToTitleCase($text.ToLower())
Write-Output $capitalizedText
```
Output:
```
Hello world
```

Note: This method capitalizes the first letter of each word. If you strictly want to capitalize only the first letter of the string and leave the rest as is, you could do something like this:

```powershell
# Capitalizing only the first character of a string
$text = "hello world"
$capitalizedText = $text.Substring(0,1).ToUpper() + $text.Substring(1)
Write-Output $capitalizedText
```
Output:
```
Hello world
```

PowerShell does not directly include a simple function for capitalizing only the first letter of a string, but by combining the basic string manipulation methods such as `Substring(0,1).ToUpper()` and concatenation, we can easily achieve the desired result.
