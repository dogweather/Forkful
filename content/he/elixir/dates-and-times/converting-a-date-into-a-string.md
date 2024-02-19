---
aliases:
- /he/elixir/converting-a-date-into-a-string/
date: 2024-01-20 17:37:02.230533-07:00
description: "\u05D2\u05D5\u05E8\u05DE\u05D9\u05DD \u05DE\u05D5\u05E8\u05DB\u05D1\u05D9\
  \u05DD \u05DB\u05DE\u05D5 \u05EA\u05D0\u05E8\u05D9\u05DB\u05D9\u05DD \u05E6\u05E8\
  \u05D9\u05DB\u05D9\u05DD \u05DC\u05D9\u05D4\u05E4\u05D5\u05DA \u05DC\u05DE\u05D7\
  \u05E8\u05D5\u05D6\u05D5\u05EA \u05DB\u05D3\u05D9 \u05DC\u05D4\u05D9\u05D5\u05EA\
  \ \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD \u05E7\u05E8\u05D9\u05D0\u05D9\u05DD. \u05EA\
  \u05DB\u05E0\u05D9\u05EA\u05E0\u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D0\
  \u05EA \u05D6\u05D4 \u05DC\u05D4\u05E6\u05D2\u05D4, \u05EA\u05D9\u05E2\u05D5\u05D3\
  \ \u05D5\u05D7\u05D9\u05DC\u05D5\u05E4\u05D9 \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD\
  ."
lastmod: 2024-02-18 23:08:52.537735
model: gpt-4-1106-preview
summary: "\u05D2\u05D5\u05E8\u05DE\u05D9\u05DD \u05DE\u05D5\u05E8\u05DB\u05D1\u05D9\
  \u05DD \u05DB\u05DE\u05D5 \u05EA\u05D0\u05E8\u05D9\u05DB\u05D9\u05DD \u05E6\u05E8\
  \u05D9\u05DB\u05D9\u05DD \u05DC\u05D9\u05D4\u05E4\u05D5\u05DA \u05DC\u05DE\u05D7\
  \u05E8\u05D5\u05D6\u05D5\u05EA \u05DB\u05D3\u05D9 \u05DC\u05D4\u05D9\u05D5\u05EA\
  \ \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD \u05E7\u05E8\u05D9\u05D0\u05D9\u05DD. \u05EA\
  \u05DB\u05E0\u05D9\u05EA\u05E0\u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D0\
  \u05EA \u05D6\u05D4 \u05DC\u05D4\u05E6\u05D2\u05D4, \u05EA\u05D9\u05E2\u05D5\u05D3\
  \ \u05D5\u05D7\u05D9\u05DC\u05D5\u05E4\u05D9 \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD\
  ."
title: "\u05D4\u05DE\u05E8\u05EA \u05EA\u05D0\u05E8\u05D9\u05DA \u05DC\u05DE\u05D7\
  \u05E8\u05D5\u05D6\u05EA"
---

{{< edit_this_page >}}

## What & Why? (מה ולמה?)
גורמים מורכבים כמו תאריכים צריכים ליהפוך למחרוזות כדי להיות נתונים קריאים. תכניתנים עושים את זה להצגה, תיעוד וחילופי נתונים.

## How to: (איך לעשות:)
```elixir
# יצירת תאריך
date = ~D[2023-04-14]

# המרה למחרוזת בפורמט ברירת מחדל
date_string_default = to_string(date)
IO.puts(date_string_default) # פלט: "2023-04-14"

# המרה למחרוזת באמצעות Calendar.strftime
date_string_custom = Date.to_string(date, "{YYYY}-{M}-{D}")
IO.puts(date_string_custom) # פלט: "2023-4-14"
```

## Deep Dive (עומק הנושא)
בעבר, יש מי שהשתמש במודולים חיצוניים כמו Timex כדי לעבוד עם תאריכים. כיום, Elixir מספק את מודול Date לעבודה מובנית עם תאריכים ולביצוע המרות. קיימים אף פורמטים רבים ומגוונים שניתן להשתמש בהם כדי להמיר תאריך למחרוזת.

Calendar.strftime מאפשר גמישות רבה בהמרת תאריכים למחרוזות עם פורמט מותאם אישית. Elixir משתמש ביכולות הזמן של Erlang, שעליהן הוא בנוי, ומרחיב אותן לשימוש ידידותי יותר.

## See Also (ראו גם)
- [Elixir Date Documentation](https://hexdocs.pm/elixir/Date.html) – הדוקומנטציה הרשמית עבור התמיכה בתאריכים ב-Elixir.
- [Erlang's Calendar Module](http://erlang.org/doc/man/calendar.html) – ידע קצת יותר עמוק על היכולות של Erlang, עליהן Elixir נשען.
