---
aliases:
- /he/elm/converting-a-string-to-lower-case/
date: 2024-01-20 17:38:52.826337-07:00
description: "\u05D4\u05DE\u05E8\u05D4 \u05E9\u05DC \u05DE\u05D7\u05E8\u05D5\u05D6\
  \u05EA \u05DC\u05D0\u05D5\u05EA\u05D9\u05D5\u05EA \u05E7\u05D8\u05E0\u05D5\u05EA\
  \ \u05D6\u05D4 \u05E4\u05E9\u05D5\u05D8 \u05DC\u05E7\u05D7\u05EA \u05D8\u05E7\u05E1\
  \u05D8 \u05D5\u05DC\u05D4\u05E4\u05D5\u05DA \u05D0\u05EA \u05DB\u05DC \u05D4\u05D0\
  \u05D5\u05EA\u05D9\u05D5\u05EA \u05D4\u05D2\u05D3\u05D5\u05DC\u05D5\u05EA \u05DC\
  \u05E7\u05D8\u05E0\u05D5\u05EA. \u05EA\u05D5\u05DB\u05E0\u05D9\u05EA\u05E0\u05D9\
  \u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D0\u05EA \u05D6\u05D4 \u05DB\u05D3\u05D9\
  \ \u05DC\u05D0\u05D7\u05D3 \u05E4\u05D5\u05E8\u05DE\u05D8\u05D9\u05DD, \u05DC\u05D4\
  \u05E7\u05DC \u05E2\u05DC \u05D4\u05E9\u05D5\u05D5\u05D0\u05D5\u05EA \u05D8\u05E7\
  \u05E1\u05D8, \u05D5\u05DC\u05E9\u05DE\u05D5\u05E8\u2026"
lastmod: 2024-02-18 23:08:52.739837
model: gpt-4-1106-preview
summary: "\u05D4\u05DE\u05E8\u05D4 \u05E9\u05DC \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA\
  \ \u05DC\u05D0\u05D5\u05EA\u05D9\u05D5\u05EA \u05E7\u05D8\u05E0\u05D5\u05EA \u05D6\
  \u05D4 \u05E4\u05E9\u05D5\u05D8 \u05DC\u05E7\u05D7\u05EA \u05D8\u05E7\u05E1\u05D8\
  \ \u05D5\u05DC\u05D4\u05E4\u05D5\u05DA \u05D0\u05EA \u05DB\u05DC \u05D4\u05D0\u05D5\
  \u05EA\u05D9\u05D5\u05EA \u05D4\u05D2\u05D3\u05D5\u05DC\u05D5\u05EA \u05DC\u05E7\
  \u05D8\u05E0\u05D5\u05EA. \u05EA\u05D5\u05DB\u05E0\u05D9\u05EA\u05E0\u05D9\u05DD\
  \ \u05E2\u05D5\u05E9\u05D9\u05DD \u05D0\u05EA \u05D6\u05D4 \u05DB\u05D3\u05D9 \u05DC\
  \u05D0\u05D7\u05D3 \u05E4\u05D5\u05E8\u05DE\u05D8\u05D9\u05DD, \u05DC\u05D4\u05E7\
  \u05DC \u05E2\u05DC \u05D4\u05E9\u05D5\u05D5\u05D0\u05D5\u05EA \u05D8\u05E7\u05E1\
  \u05D8, \u05D5\u05DC\u05E9\u05DE\u05D5\u05E8\u2026"
title: "\u05D4\u05DE\u05E8\u05EA \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05DC\u05D0\
  \u05D5\u05EA\u05D9\u05D5\u05EA \u05E7\u05D8\u05E0\u05D5\u05EA"
---

{{< edit_this_page >}}

## מה ולמה?
המרה של מחרוזת לאותיות קטנות זה פשוט לקחת טקסט ולהפוך את כל האותיות הגדולות לקטנות. תוכניתנים עושים את זה כדי לאחד פורמטים, להקל על השוואות טקסט, ולשמור על עקביות בבסיסי נתונים.

## איך לעשות:
באלם זה פשוט מאוד. תשתמשו בפונקציה `String.toLower` כדי להמיר כל מחרוזת שברצונכם.

```Elm
import String

lowercaseString : String -> String
lowercaseString str =
  String.toLower str

-- דוגמא לשימוש:
result : String
result =
  lowercaseString "HELLO, WORLD!"

-- תוצאה:
-- "hello, world!"
```

## עיון מעמיק
המרה לאותיות קטנות היא משימה סטנדרטית בתכנות, ואפשר היה למצוא אותה כבר בשפות עתיקות כמו לימוד שפת מ"א. ישנם חלופות כמו השימוש בביטויים רגולריים או פונקציות עזר מותאמות אישית, אבל באלם, 'String.toLower' היא פונקציה פשוטה וישירה שעושה את העבודה. מאחורי הקלעים, הפונקציה חייבת לכבד כללים של השפה, כמו אותיות גדולות בשפות שונות וסימנים מיוחדים.

## ראו גם
- תיעוד הפונקציה `String.toLower` באלם: [https://package.elm-lang.org/packages/elm/core/latest/String#toLower](https://package.elm-lang.org/packages/elm/core/latest/String#toLower)
- מדריך לעבודה עם טקסט ומחרוזות בסטנדרטים שונים.
