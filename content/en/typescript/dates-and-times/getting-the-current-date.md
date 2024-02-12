---
title:                "Getting the current date"
aliases:
- en/typescript/getting-the-current-date.md
date:                  2024-02-03T19:02:32.159644-07:00
model:                 gpt-4-0125-preview
simple_title:         "Getting the current date"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/typescript/getting-the-current-date.md"
---

{{< edit_this_page >}}

## What & Why?
Getting the current date in TypeScript, a language built on JavaScript, allows you to access and manipulate the current date and time information. Programmers often need this functionality for creating timestamps, scheduling, and other time-sensitive features in their applications.

## How to:
In TypeScript, you can use the `Date` object to get the current date and time. Here’s how you can do it:

```typescript
const currentDate = new Date();
console.log(currentDate);
```

Sample output:
```
2023-04-12T07:20:50.52Z
```

This code snippet creates a new `Date` object containing the current date and time, which is then printed to the console. You can also format the date using toLocaleDateString() for more readable formats:

```typescript
const currentDate = new Date();
console.log(currentDate.toLocaleDateString());
```

Sample output:
```
4/12/2023
```

### Using date-fns
For more extensive date manipulation and formatting, the `date-fns` library is a popular choice. First, install it via npm:

```bash
npm install date-fns
```

Then, you can use it to format the current date:

```typescript
import { format } from 'date-fns';

const currentDate = new Date();
console.log(format(currentDate, 'yyyy-MM-dd'));
```

Sample output:
```
2023-04-12
```

This `date-fns` example formats the current date as a string in "YYYY-MM-DD" format. The library offers a plethora of functions for date manipulation, making it a versatile tool for any TypeScript programmer working with dates.
