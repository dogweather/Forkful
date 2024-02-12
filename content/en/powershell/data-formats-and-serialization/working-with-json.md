---
title:                "Working with JSON"
aliases:
- en/powershell/working-with-json.md
date:                  2024-02-03T19:02:58.472005-07:00
model:                 gpt-4-0125-preview
simple_title:         "Working with JSON"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/powershell/working-with-json.md"
---

{{< edit_this_page >}}

## What & Why?

PowerShell's integration with JSON (JavaScript Object Notation) is about parsing (reading) and generating (writing) JSON data, a common format for data exchange on the web. Programmers work with JSON to interact with web APIs, configuration files, or to facilitate data interchange between different languages and platforms due to its lightweight and language-independent nature.

## How to:

### Parsing JSON

To read or parse JSON in PowerShell, you can use the `ConvertFrom-Json` cmdlet. Given a JSON string, this cmdlet converts it into a PowerShell object. 

```powershell
$json = '{"name": "John Doe", "age": 30, "city": "New York"}'
$person = $json | ConvertFrom-Json
$person.name
```

Sample output:

```
John Doe
```

This example demonstrates how to parse a simple JSON string to access properties of the resulting object.

### Generating JSON

To generate JSON from a PowerShell object, you can use the `ConvertTo-Json` cmdlet. This is handy for preparing data to be sent to a web service or saved into a configuration file.

```powershell
$person = [PSCustomObject]@{
    name = "Jane Doe"
    age = 25
    city = "Los Angeles"
}
$json = $person | ConvertTo-Json
Write-Output $json
```

Sample output:

```json
{
    "name":  "Jane Doe",
    "age":  25,
    "city":  "Los Angeles"
}
```

This code snippet creates a PowerShell object and then converts it to a JSON string.
