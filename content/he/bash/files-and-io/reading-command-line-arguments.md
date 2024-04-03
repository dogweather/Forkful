---
date: 2024-01-20 17:55:33.818376-07:00
description: "\u05E7\u05E8\u05D9\u05D0\u05EA \u05D0\u05E8\u05D2\u05D5\u05DE\u05E0\u05D8\
  \u05D9\u05DD \u05DE\u05E9\u05D5\u05E8\u05EA \u05D4\u05E4\u05E7\u05D5\u05D3\u05D4\
  \ \u05DE\u05D0\u05E4\u05E9\u05E8\u05EA \u05DC\u05E7\u05D1\u05D5\u05E2 \u05D0\u05D5\
  \u05E4\u05E6\u05D9\u05D5\u05EA \u05D5\u05E4\u05E8\u05DE\u05D8\u05E8\u05D9\u05DD\
  \ \u05DC\u05EA\u05D5\u05DB\u05E0\u05D9\u05EA \u05DE\u05D1\u05DC\u05D9 \u05DC\u05E9\
  \u05E0\u05D5\u05EA \u05D0\u05EA \u05D4\u05E7\u05D5\u05D3 \u05E2\u05E6\u05DE\u05D5\
  . \u05EA\u05DB\u05E0\u05D5\u05EA \u05DB\u05D6\u05D4 \u05DE\u05D0\u05E4\u05E9\u05E8\
  \ \u05D2\u05DE\u05D9\u05E9\u05D5\u05EA \u05E8\u05D1\u05D4 \u05D5\u05E9\u05D9\u05DE\
  \u05D5\u05E9 \u05D7\u05D5\u05D6\u05E8 \u05D1\u05E7\u05D5\u05D3 \u05DC\u05DE\u05D2\
  \u05D5\u05D5\u05DF \u05E1\u05D9\u05D8\u05D5\u05D0\u05E6\u05D9\u05D5\u05EA."
lastmod: '2024-03-13T22:44:39.650519-06:00'
model: gpt-4-1106-preview
summary: "\u05E7\u05E8\u05D9\u05D0\u05EA \u05D0\u05E8\u05D2\u05D5\u05DE\u05E0\u05D8\
  \u05D9\u05DD \u05DE\u05E9\u05D5\u05E8\u05EA \u05D4\u05E4\u05E7\u05D5\u05D3\u05D4\
  \ \u05DE\u05D0\u05E4\u05E9\u05E8\u05EA \u05DC\u05E7\u05D1\u05D5\u05E2 \u05D0\u05D5\
  \u05E4\u05E6\u05D9\u05D5\u05EA \u05D5\u05E4\u05E8\u05DE\u05D8\u05E8\u05D9\u05DD\
  \ \u05DC\u05EA\u05D5\u05DB\u05E0\u05D9\u05EA \u05DE\u05D1\u05DC\u05D9 \u05DC\u05E9\
  \u05E0\u05D5\u05EA \u05D0\u05EA \u05D4\u05E7\u05D5\u05D3 \u05E2\u05E6\u05DE\u05D5\
  ."
title: "\u05E7\u05E8\u05D9\u05D0\u05EA \u05E4\u05E8\u05DE\u05D8\u05E8\u05D9\u05DD\
  \ \u05DE\u05E9\u05D5\u05E8\u05EA \u05D4\u05E4\u05E7\u05D5\u05D3\u05D4"
weight: 23
---

## איך לעשות:
קוד Bash הבסיסי לקריאת ארגומנטים:
```Bash
#!/bin/bash
echo "הארגומנט הראשון שהתקבל הוא: $1"
echo "הארגומנט השני שהתקבל הוא: $2"
echo "כל הארגומנטים שהתקבלו: $@"
echo "מספר הארגומנטים שהתקבלו: $#"
```
פלט לדוגמא כאשר הסקריפט נקרא עם שני ארגומנטים:
```
הארגומנט הראשון שהתקבל הוא: פרמטר1
הארגומנט השני שהתקבל הוא: פרמטר2
כל הארגומנטים שהתקבלו: פרמטר1 פרמטר2
מספר הארגומנטים שהתקבלו: 2
```

## טבילה עמוקה
בימי הדוס הקדומים, פרמטרים נקראו ישירות משורת הפקודה. ב-Linux, שורת הפקודה עדיין משמשת לזה. ארגומנטים מועברים לסקריפטים ותוכניות כמערך של מחרוזות, וניתנים לגישה באמצעות משתנים מיוחדים (`$1`, `$2`, ..., `$@`, `$#`). יש גם אלטרנטיבות כמו `getopt` ו-`getopts` לעיבוד מתקדם יותר של ארגומנטים. פרטי היישום משתנים בהתאם לצרכים: בדיקת תקינות, קריאת אופציות, הגדרת ערכים ברירת מחדל ועוד.

## ראה גם
- טוטוריאלים רשמיים ל-Bash: [GNU Bash Manual](https://www.gnu.org/software/bash/manual/bash.html)
- מדריך מפורט על כתיבת סקריפטים ב-Bash: [Advanced Bash-Scripting Guide](http://www.tldp.org/LDP/abs/html/)
