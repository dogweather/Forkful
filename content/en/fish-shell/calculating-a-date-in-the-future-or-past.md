---
title:                "Calculating a date in the future or past"
date:                  2024-01-20T17:30:42.415931-07:00
model:                 gpt-4-1106-preview
simple_title:         "Calculating a date in the future or past"
programming_language: "Fish Shell"
category:             "Fish Shell"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/fish-shell/calculating-a-date-in-the-future-or-past.md"
---

{{< edit_this_page >}}

## What & Why?
Calculating a future or past date involves manipulating dates to find out what day it was or will be. Programmers do this for scheduling, reminders, or determining durations and deadlines.

## How to:
Here's a cool way of rolling with dates in Fish Shell:

```Fish Shell
# Add days to the current date
set -l days_to_add 10
date -d "+$days_to_add days"

# Output example (varies by current date):
# Wed Mar 29 00:29:10 PDT 2023

# Subtract days from the current date
set -l days_to_subtract 10
date -d "-$days_to_subtract days"

# Output example (again, your date may vary):
# Sun Mar 9 00:30:42 PDT 2023
```

## Deep Dive
Fish isn't all about the splash; it comes with history. Shells like bash used to be the go-to for date calculations, typically through GNU `date`. Fish, keeping it streamlined, uses similar syntax but can be more user-friendly and readable – great for both swimming newbies and seasoned trout.

Alternatives for date calculations include programming languages like Python or using `dateutils`. Each has its own strengths, though `dateutils` is a bit more obscure and Python might be overkill for simple tasks. Implementation in Fish is a middle ground, with the `date` command borrowing from UNIX standards – it's pretty much installed everywhere and ties into system time settings smoothly.

## See Also
For more details, dive into these waters:
- [GNU Coreutils – Date](https://www.gnu.org/software/coreutils/manual/html_node/date-invocation.html): Get a grasp of how `date` works under the hood.
- [The Fish Shell Documentation](https://fishshell.com/docs/current/index.html): Official docs, where you can learn about Fish and its other commands.
- [StackOverflow: Date Arithmetic](https://stackoverflow.com/questions/tagged/date-arithmetic): See real-world problems and solutions from the community.
