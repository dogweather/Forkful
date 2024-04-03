---
date: 2024-01-26 03:40:31.547865-07:00
description: "\u05D4\u05E1\u05E8\u05EA \u05DE\u05E8\u05DB\u05D0\u05D5\u05EA \u05DE\
  \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05D0\u05D5\u05DE\u05E8\u05EA \u05DC\u05E0\
  \u05E7\u05D5\u05EA \u05D0\u05EA \u05D0\u05D5\u05EA\u05DD \u05E1\u05D9\u05DE\u05E0\
  \u05D9 \u05DE\u05E8\u05DB\u05D0\u05D5\u05EA \u05DB\u05E4\u05D5\u05DC\u05D5\u05EA\
  \ \u05D0\u05D5 \u05D9\u05D7\u05D9\u05D3\u05D5\u05EA \u05DE\u05D9\u05D5\u05EA\u05E8\
  \u05D5\u05EA \u05E9\u05D0\u05D9\u05E0\u05DA \u05E6\u05E8\u05D9\u05DA \u05D1\u05D0\
  \u05DE\u05EA \u05D1\u05D8\u05E7\u05E1\u05D8 \u05D4\u05DE\u05E2\u05D5\u05D1\u05D3\
  . \u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\
  \u05EA \u05DB\u05D3\u05D9 \u05DC\u05E0\u05E7\u05D5\u05EA \u05E7\u05DC\u05D8, \u05DC\
  \u05D4\u05DB\u05D9\u05DF \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD\u2026"
lastmod: '2024-03-13T22:44:39.181940-06:00'
model: gpt-4-0125-preview
summary: "\u05D4\u05E1\u05E8\u05EA \u05DE\u05E8\u05DB\u05D0\u05D5\u05EA \u05DE\u05DE\
  \u05D7\u05E8\u05D5\u05D6\u05EA \u05D0\u05D5\u05DE\u05E8\u05EA \u05DC\u05E0\u05E7\
  \u05D5\u05EA \u05D0\u05EA \u05D0\u05D5\u05EA\u05DD \u05E1\u05D9\u05DE\u05E0\u05D9\
  \ \u05DE\u05E8\u05DB\u05D0\u05D5\u05EA \u05DB\u05E4\u05D5\u05DC\u05D5\u05EA \u05D0\
  \u05D5 \u05D9\u05D7\u05D9\u05D3\u05D5\u05EA \u05DE\u05D9\u05D5\u05EA\u05E8\u05D5\
  \u05EA \u05E9\u05D0\u05D9\u05E0\u05DA \u05E6\u05E8\u05D9\u05DA \u05D1\u05D0\u05DE\
  \u05EA \u05D1\u05D8\u05E7\u05E1\u05D8 \u05D4\u05DE\u05E2\u05D5\u05D1\u05D3."
title: "\u05D4\u05E1\u05E8\u05EA \u05DE\u05E8\u05DB\u05D0\u05D5\u05EA \u05DE\u05DE\
  \u05D7\u05E8\u05D5\u05D6\u05EA"
weight: 9
---

## איך לעשות:
ב-Elm, תוכל להשתמש בפונקציות של `String` כדי לשנות מחרוזות, כמו להסיר מרכאות. הנה דרך ישירה לעשות זאת:

```Elm
removeQuotes : String -> String
removeQuotes str =
    String.trim (String.filter (\char -> char /= '\"' && char /= '\'') str)

main =
    String.removeQuotes "\"This is a 'quoted' string!\""
    -- פלט: This is a quoted string!
```

פשוט זכור: החתיכה הקטנה הזו תסיר את כל המרכאות מהמחרוזת שלך, אז השתמש בה בחוכמה!

## טבילה עמוקה
בימים ההם, להתמודד עם מחרוזות היה דורש הרבה יותר עבודת יד, כולל ניתוח ידני רב. כיום, שפות כמו Elm מפשטות את זה עם פונקציות מובנות. הפונקציה `String.filter` היא כלי גמיש בארסנל שלך עבור כאשר אתה צריך להתעסק בכל תו, שכולל אך לא מוגבל למשיכת מרכאות.

כחלופה, ייתכן שתעדיף להשתמש בביטויים רגולריים אם Elm הייתה תומכת בהם בצורה ניידת, שלא קיימת כברירת מחדל. אבל היי, התמקדות Elm בפשטות ובטיחות אומרת שהגישה שלנו של `String.filter` היא ברורה, בטוחה, וקלה לתחזוק.

הגישה הפונקציונלית של Elm מעודדת פונקציות טהורות ללא תופעות לוואי, ו`removeQuotes` הוא דוגמה טובה לכך. היא לוקחת מחרוזת ומחזירה חדשה, תוך שהיא משאירה את המקורית ללא נזק. זוהי משחקיות המבני נתונים בלתי ניתנים לשינוי של Elm, שמקדמים צפייה ומקלים על כאבי הניפוי שגיאות שלך.

## ראה גם
לקריאה נוספת והרפתקאות נוספות של ניפוי מחרוזות, בדוק את התיעוד של מודול `String` של Elm ב:

- [תיעוד String של Elm](https://package.elm-lang.org/packages/elm/core/latest/String)

ואם אי פעם אתה נתקל בקושי לגבי מה Elm תומכת בנוגע לטיפול במחרוזות או כל תכונת שפה:

- [מדריך שפת Elm](https://guide.elm-lang.org/)
