---
date: 2024-01-20 17:32:10.315216-07:00
description: "\u05D7\u05D9\u05E9\u05D5\u05D1 \u05EA\u05D0\u05E8\u05D9\u05DA \u05D1\
  \u05E2\u05EA\u05D9\u05D3 \u05D0\u05D5 \u05D1\u05E2\u05D1\u05E8 \u05D4\u05D5\u05D0\
  \ \u05D4\u05EA\u05D4\u05DC\u05D9\u05DA \u05E9\u05D1\u05D5 \u05D0\u05E0\u05D5 \u05DE\
  \u05E1\u05EA\u05DB\u05DC\u05D9\u05DD \u05DE\u05E8\u05D0\u05E9 \u05D0\u05D5 \u05DC\
  \u05D0\u05D7\u05D5\u05E8 \u05D1\u05D6\u05DE\u05DF \u05DE\u05D4\u05EA\u05D0\u05E8\
  \u05D9\u05DA \u05D4\u05E0\u05D5\u05DB\u05D7\u05D9. \u05EA\u05DB\u05E0\u05EA\u05D9\
  \u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D0\u05EA \u05D6\u05D4 \u05DB\u05D3\u05D9\
  \ \u05DC\u05E0\u05D4\u05DC \u05DC\u05D5\u05D7\u05D5\u05EA \u05D6\u05DE\u05E0\u05D9\
  \u05DD, \u05EA\u05D6\u05DB\u05D5\u05E8\u05D5\u05EA, \u05D0\u05D5 \u05DC\u05D7\u05E9\
  \u05D1 \u05D4\u05E4\u05E8\u05E9\u05D9\u2026"
lastmod: '2024-03-13T22:44:39.573006-06:00'
model: gpt-4-1106-preview
summary: "\u05D7\u05D9\u05E9\u05D5\u05D1 \u05EA\u05D0\u05E8\u05D9\u05DA \u05D1\u05E2\
  \u05EA\u05D9\u05D3 \u05D0\u05D5 \u05D1\u05E2\u05D1\u05E8 \u05D4\u05D5\u05D0 \u05D4\
  \u05EA\u05D4\u05DC\u05D9\u05DA \u05E9\u05D1\u05D5 \u05D0\u05E0\u05D5 \u05DE\u05E1\
  \u05EA\u05DB\u05DC\u05D9\u05DD \u05DE\u05E8\u05D0\u05E9 \u05D0\u05D5 \u05DC\u05D0\
  \u05D7\u05D5\u05E8 \u05D1\u05D6\u05DE\u05DF \u05DE\u05D4\u05EA\u05D0\u05E8\u05D9\
  \u05DA \u05D4\u05E0\u05D5\u05DB\u05D7\u05D9."
title: "\u05D7\u05D9\u05E9\u05D5\u05D1 \u05EA\u05D0\u05E8\u05D9\u05DA \u05D1\u05E2\
  \u05EA\u05D9\u05D3 \u05D0\u05D5 \u05D1\u05E2\u05D1\u05E8"
weight: 26
---

## איך לעשות:
ב-Lua, אין מודול ברירת מחדל לעבודה עם תאריכים, אבל אפשר להשתמש ב`os` לקבלת הזמן הנוכחי ולחשב ממנו.

```lua
local seconds_in_day = 86400 -- 24 שעות, 60 דקות, 60 שניות
local current_time = os.time() -- זמן UNIX נוכחי
local future_time = current_time + (seconds_in_day * 10) -- תאריך בעוד 10 ימים
local past_time = current_time - (seconds_in_day * 10) -- תאריך לפני 10 ימים

print("התאריך הנוכחי:", os.date("%x", current_time))
print("התאריך בעוד 10 ימים:", os.date("%x", future_time))
print("התאריך לפני 10 ימים:", os.date("%x", past_time))
```

פלט לדוגמא:
```
התאריך הנוכחי: 03/16/23
התאריך בעוד 10 ימים: 03/26/23
התאריך לפני 10 ימים: 03/06/23
```

## צלילה לעומק:
ב-Lua, מודול ה`os` מספק דרך פשוטה לעבוד עם תאריכים. בשפות אחרות יש ספריות יותר מורכבות לניהול תאריכים וזמנים. לפני שיפוץ שפת Lua, היו נקודות זמן מוגבלות לתאריכים שהם 32-ביט, אך כיום, עם תאריכי 64-ביט, Lua יכולה לייצג תאריכים רחוקים מאוד.

לחישוב תאריכים מדויקים יותר (למשל, תחשיב עם שעות קפיצה ושנים מעוברות), כדאי לעבוד עם ספרייה חיצונית כמו `luadate`. היא מוסיפה תמיכה באזורי זמן ומתקנים לקפיצות.

במקרה שבו דרושים חישובים עם מדויק גבוה יותר או תמיכה בקלנדרים שונים, פתרונות אחרים עשויים להתברר כדרושים. בכל זאת, עבור מטלות יומיומיות בסיסיות, מודול ה`os` שב-Lua בדרך כלל מספיק.

## ראו גם:
- [מסמכי Lua 5.4 - os.date](https://www.lua.org/manual/5.4/manual.html#pdf-os.date)
- [ספריית luadate](https://github.com/Tieske/date)
