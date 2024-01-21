---
title:                "חילוץ תת-מחרוזות"
date:                  2024-01-20T17:46:05.731657-07:00
model:                 gpt-4-1106-preview
simple_title:         "חילוץ תת-מחרוזות"
programming_language: "Lua"
category:             "Lua"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/lua/extracting-substrings.md"
---

{{< edit_this_page >}}

## What & Why?
מה זה חלקי מחרוזות (substrings) ולמה אנחנו צריכים להשיג אותם? ההוצאה של חלקי מחרוזת זה כאשר אנו בוחרים חלק מסוים של מחרוזת ומבודדים אותו. תוכנתנים עושים זאת כדי לנתח נתונים, לולאות (validate) קלטים ולעבד מידע בצורה יעילה.

## How to:
הנה איך מוציאים חלקי מחרוזת ב-Lua:
```lua
-- דוגמא 1: קבלת חלק מהתחלה עם רשימת פרמטרים
local text = "שלום עולם"
local subtext = text:sub(1, 5)
print(subtext)  -- יוצא "שלום"

-- דוגמא 2: קבלת חלק מסוף ללא פרמטר שני
local subtext_end = text:sub(-5)
print(subtext_end)  -- יוצא "עולם"

-- דוגמא 3: קבלת תת-מחרוזת באמצעות תבנית (pattern)
local pattern_subtext = string.match(text, "עול(.*)")
print(pattern_subtext)  -- יוצא "ם"
```

## Deep Dive
הוצאת חלקי מחרוזת היא פונקציה בסיסית שניתן למצוא ברוב שפות התכנות. ב-Lua, הפונקציה `sub` מופיעה בגרסה 5 ומעלה. יש גם שיטות אלטרנטיביות כמו שימוש בביטויים רגולריים באמצעות המודול 'string'. היעילות של ההוצאה תלויה בגודל המחרוזת ובפונקציה שבחרת להשתמש.

## See Also
- התיעוד הרשמי של Lua לעבודה עם מחרוזות: http://www.lua.org/manual/5.4/manual.html#6.4
- מדריך לשימוש בביטויים רגולריים ב-Lua: https://www.lua.org/pil/20.2.html
- פורום Stack Overflow של Lua לשאלות נפוצות: https://stackoverflow.com/questions/tagged/lua