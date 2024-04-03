---
date: 2024-01-26 03:44:47.052960-07:00
description: "\u05E2\u05D9\u05D2\u05D5\u05DC \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD\
  \ \u05E2\u05D5\u05E1\u05E7 \u05D1\u05D7\u05D9\u05EA\u05D5\u05DA \u05DE\u05E7\u05D5\
  \u05DE\u05D5\u05EA \u05E2\u05E9\u05E8\u05D5\u05E0\u05D9\u05D9\u05DD \u05DB\u05D3\
  \u05D9 \u05DC\u05E4\u05E9\u05D8 \u05D0\u05EA \u05D4\u05E0\u05EA\u05D5\u05E0\u05D9\
  \u05DD \u05D0\u05D5 \u05DC\u05D4\u05EA\u05D0\u05D9\u05DE\u05DD \u05DC\u05E4\u05D5\
  \u05E8\u05DE\u05D8\u05D9\u05DD \u05E1\u05E4\u05E6\u05D9\u05E4\u05D9\u05D9\u05DD\
  . \u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\
  \u05EA \u05DC\u05E6\u05D5\u05E8\u05DA \u05D4\u05E6\u05D2\u05D4 \u05D9\u05D3\u05D9\
  \u05D3\u05D5\u05EA\u05D9\u05EA \u05DC\u05DE\u05E9\u05EA\u05DE\u05E9, \u05D0\u05D7\
  \u05E1\u05D5\u05DF \u05D9\u05E2\u05D9\u05DC, \u05D0\u05D5\u2026"
lastmod: '2024-03-13T22:44:40.036646-06:00'
model: gpt-4-0125-preview
summary: "\u05E2\u05D9\u05D2\u05D5\u05DC \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD \u05E2\
  \u05D5\u05E1\u05E7 \u05D1\u05D7\u05D9\u05EA\u05D5\u05DA \u05DE\u05E7\u05D5\u05DE\
  \u05D5\u05EA \u05E2\u05E9\u05E8\u05D5\u05E0\u05D9\u05D9\u05DD \u05DB\u05D3\u05D9\
  \ \u05DC\u05E4\u05E9\u05D8 \u05D0\u05EA \u05D4\u05E0\u05EA\u05D5\u05E0\u05D9\u05DD\
  \ \u05D0\u05D5 \u05DC\u05D4\u05EA\u05D0\u05D9\u05DE\u05DD \u05DC\u05E4\u05D5\u05E8\
  \u05DE\u05D8\u05D9\u05DD \u05E1\u05E4\u05E6\u05D9\u05E4\u05D9\u05D9\u05DD."
title: "\u05E2\u05D9\u05D2\u05D5\u05DC \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD"
weight: 13
---

## איך לעשות:
ב-Fish, עיגול מספרים מתבצע בעזרת הפקודה `math`. השתמשו ב-`math -s0` כדי לעגל לשלם הקרוב ביותר.

```fish
# עיגול למעלה
echo (math -s0 "4.7")
# פלט: 5

# עיגול למטה
echo (math -s0 "4.3")
# פלט: 4

# עיגול לשני מקומות עשרוניים
echo (math -s2 "4.5678")
# פלט: 4.57

# עיגול מספר שלילי
echo (math -s0 "-2.5")
# פלט: -3
```

## צלילה עמוקה
בהיסטוריה, עיגול מספרים היה נעשה באופן יותר ידני או עם כלים חיצוניים, אבל בשרלים מודרניים כמו Fish, זה משולב בתוך הכלים המובנים. הגישה של Fish באמצעות הפקודה `math` מפשטת דברים בהשוואה לשרלים ישנים יותר. האלטרנטיבות בסביבות תכנות אחרות משתנות; שפות כמו Python משתמשות בפונקציות כמו `round()`, בעוד שב-Bash ייתכן שידרשו ביטויים מורכבים יותר או השימוש בכלי `bc`. היישום של עיגול מספרים ב-Fish מפשט את כתיבת תסריטים על ידי שמירת המתמטיקה בתוך הסביבה של השרל, במקום להזמין כלים או שפות אחרות.

## ראו גם
- תיעוד Fish עבור הפקודה `math`: https://fishshell.com/docs/current/cmds/math.html
- התקן IEEE לחישוב עשרוני צף (IEEE 754): https://ieeexplore.ieee.org/document/4610935
