---
aliases:
- /en/python/getting-the-current-date/
date: 2024-02-03 19:02:38.431289-07:00
description: "Fetching the current date in Python is a staple operation for many applications,\
  \ such as logging, data analysis, and time-based decision-making. It's\u2026"
lastmod: 2024-02-18 23:09:10.691909
model: gpt-4-0125-preview
summary: "Fetching the current date in Python is a staple operation for many applications,\
  \ such as logging, data analysis, and time-based decision-making. It's\u2026"
title: Getting the current date
---

{{< edit_this_page >}}

## What & Why?

Fetching the current date in Python is a staple operation for many applications, such as logging, data analysis, and time-based decision-making. It's about retrieving the system's current date, which is crucial for tasks that depend on temporal context.

## How to:

**Using the standard library `datetime`:**

The `datetime` module in Python's standard library provides classes for manipulating dates and times. To get the current date, you can use the `date.today()` method.

```python
from datetime import date

today = date.today()
print(today)  # Output: YYYY-MM-DD (e.g., 2023-04-05)
```

**Time Formatting:**

If you require the current date in a different format, the `strftime` method allows you to specify custom date formatting:

```python
from datetime import date

today = date.today()
formatted_date = today.strftime('%B %d, %Y')  # Example format: "April 05, 2023"
print(formatted_date)
```

**Using `pendulum` for more flexibility (a popular third-party library):**

`Pendulum` is a third-party library that offers a more intuitive approach to dealing with dates and times in Python. It extends the standard datetime functionalities and simplifies time zone management, among other features.

First, ensure you've installed `pendulum` via pip:

```shell
pip install pendulum
```

Then, to get the current date:

```python
import pendulum

today = pendulum.now().date()
print(today)  # Output: YYYY-MM-DD (e.g., 2023-04-05)
```

With `pendulum`, formatting is also straightforward and similar to the `strftime` approach:

```python
import pendulum

today = pendulum.now()
formatted_date = today.to_formatted_date_string()  # Default format: "Apr 5, 2023"
print(formatted_date)
```
