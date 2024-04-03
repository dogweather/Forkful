---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:10:05.489031-07:00
description: "\u05DC\u05E7\u05D1\u05DC \u05D0\u05EA \u05D4\u05EA\u05D0\u05E8\u05D9\
  \u05DA \u05D4\u05E0\u05D5\u05DB\u05D7\u05D9 \u05D1\u05EA\u05DB\u05E0\u05D5\u05EA\
  \ \u05D4\u05D5\u05D0 \u05DE\u05E9\u05D9\u05DE\u05D4 \u05D9\u05E1\u05D5\u05D3\u05D9\
  \u05EA \u05E9\u05DE\u05D0\u05E4\u05E9\u05E8\u05EA \u05DC\u05E9\u05DC\u05D5\u05E3\
  \ \u05D5\u05DC\u05E2\u05D1\u05D3 \u05E0\u05EA\u05D5\u05E0\u05D9 \u05EA\u05D0\u05E8\
  \u05D9\u05DA \u05D5\u05E9\u05E2\u05D4 \u05E9\u05DC \u05D4\u05DE\u05E2\u05E8\u05DB\
  \u05EA. \u05D1\u05DB\u05EA\u05D9\u05D1\u05EA \u05E1\u05E7\u05E8\u05D9\u05E4\u05D8\
  \u05D9\u05DD \u05D5\u05D1\u05DE\u05E9\u05D9\u05DE\u05D5\u05EA \u05D0\u05D5\u05D8\
  \u05D5\u05DE\u05E6\u05D9\u05D4, \u05D6\u05D4 \u05D7\u05D9\u05D5\u05E0\u05D9 \u05DC\
  \u05D9\u05E6\u05D9\u05E8\u05EA \u05D7\u05D5\u05EA\u05DE\u05D5\u05EA\u2026"
lastmod: '2024-03-13T22:44:40.067157-06:00'
model: gpt-4-0125-preview
summary: "\u05DC\u05E7\u05D1\u05DC \u05D0\u05EA \u05D4\u05EA\u05D0\u05E8\u05D9\u05DA\
  \ \u05D4\u05E0\u05D5\u05DB\u05D7\u05D9 \u05D1\u05EA\u05DB\u05E0\u05D5\u05EA \u05D4\
  \u05D5\u05D0 \u05DE\u05E9\u05D9\u05DE\u05D4 \u05D9\u05E1\u05D5\u05D3\u05D9\u05EA\
  \ \u05E9\u05DE\u05D0\u05E4\u05E9\u05E8\u05EA \u05DC\u05E9\u05DC\u05D5\u05E3 \u05D5\
  \u05DC\u05E2\u05D1\u05D3 \u05E0\u05EA\u05D5\u05E0\u05D9 \u05EA\u05D0\u05E8\u05D9\
  \u05DA \u05D5\u05E9\u05E2\u05D4 \u05E9\u05DC \u05D4\u05DE\u05E2\u05E8\u05DB\u05EA\
  ."
title: "\u05E7\u05D1\u05DC\u05EA \u05D4\u05EA\u05D0\u05E8\u05D9\u05DA \u05D4\u05E0\
  \u05D5\u05DB\u05D7\u05D9"
weight: 29
---

## איך לעשות:
של Fish Shell משתמש בפקודות חיצוניות כמו `date` כדי לקבל את התאריך הנוכחי, ומציע גמישות בעיצוב הפלט כפי שנדרש. הנה איך להשתמש בזה:

```fish
# הצגת התאריך הנוכחי בפורמט המוגדר כברירת מחדל
echo (date)

# דוגמת פלט: Wed 25 Oct 2023 15:42:03 BST
```

כדי להתאים אישית את פורמט התאריך, אפשר להשתמש באופציה `+` ואז בצייני פורמט:

```fish
# הצגת התאריך הנוכחי בפורמט YYYY-MM-DD
echo (date "+%Y-%m-%d")

# דוגמת פלט: 2023-10-25
```

למשימות יותר מורכבות, כמו עבודה עם חותמות זמן או ביצוע חישובים עם תאריכים, Fish Shell נשען על כלים חיצוניים כמו `date` בשל הטבע הסקריפטי שלו. הנה דוגמה לקבלת החותמת זמן UNIX הנוכחית:

```fish
# קבלת חותמת הזמן UNIX הנוכחית
echo (date "+%s")

# דוגמת פלט: 1666710123
```

וכדי להוסיף יום אחד לתאריך הנוכחי באמצעות `date`:

```fish
# הוספת יום אחד לתאריך הנוכחי
echo (date -d "+1 day" "+%Y-%m-%d")

# דוגמת פלט: 2023-10-26
```

הערה: הדוגמאות משתמשות באופציות של פקודת `date` שעובדות עם GNU coreutils. האופציות עשויות להשתנות בסביבות אחרות כמו macOS, שברירת המחדל שלו היא פקודת תאריך של BSD. תמיד כדאי להפנות ל`date --help` או לדף ה-man כדי לקבל פרטים ספציפיים לסביבה שלך.
