---
title:                "Comparing two dates"
date:                  2024-01-20T17:33:40.084046-07:00
model:                 gpt-4-1106-preview
simple_title:         "Comparing two dates"
programming_language: "PowerShell"
category:             "PowerShell"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/powershell/comparing-two-dates.md"
---

{{< edit_this_page >}}

## What & Why?

Comparing two dates in PowerShell means figuring out if one is earlier, the same, or later than the other. Programmers often do this to manage events, sort records, schedule tasks, or check data age.

## How to:

```PowerShell
# Let's grab today's date
$today = Get-Date

# And here's an arbitrary date
$someOtherDate = Get-Date "2023-03-17"

# Are they equal?
$today -eq $someOtherDate

# Is today greater (later) than the other date?
$today -gt $someOtherDate

# How about checking if it's earlier?
$today -lt $someOtherDate

# Let's see the results, shall we?

False
True
False
```

## Deep Dive

Way back in the stone ages of computing—not really, but, you know, the early days—dates were messy. We've come a long way with standards and PowerShell simplifies it further.

Here are the bits worth chewing on:
1. **History**: Computers used to handle dates in various formats, leading to possible confusion and Y2K-style bugs. PowerShell relies on .NET's `DateTime` structure, avoiding such chaos.
   
2. **Alternatives**: You could also use `Compare-Object`, or leverage methods from `[datetime]` objects like `.AddDays()` to perform calculations before comparison. Remember `Measure-Command` to test performance impacts.
   
3. **Implementation Details**: PowerShell dates are objects with their own properties and methods. Comparing dates is done with operators (`-eq`, `-lt`, `-gt`), and, thanks to operator overloading, PowerShell knows you're dealing with dates, not just strings or numbers.

At the assembly level, date comparison translates to ticks (100-nanosecond intervals since 1/1/0001). So you’re essentially comparing large integers, which is efficient.

## See Also

- [DateTime Structure (Microsoft Docs)](https://docs.microsoft.com/en-us/dotnet/api/system.datetime?view=net-6.0)
- [Working with Dates and Times in PowerShell (SS64.com)](https://ss64.com/ps/syntax-dateformats.html)
