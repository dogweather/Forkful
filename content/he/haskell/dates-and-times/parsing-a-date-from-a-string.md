---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:14:49.297945-07:00
description: "\u05E4\u05D9\u05E2\u05E0\u05D5\u05D7 \u05EA\u05D0\u05E8\u05D9\u05DA\
  \ \u05DE\u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05D1\u05D4\u05D0\u05E1\u05E7\u05DC\
  \ \u05DB\u05D5\u05DC\u05DC \u05D4\u05DE\u05E8\u05D4 \u05E9\u05DC \u05D9\u05D9\u05E6\
  \u05D5\u05D2\u05D9\u05DD \u05D8\u05E7\u05E1\u05D8\u05D5\u05D0\u05DC\u05D9\u05D9\u05DD\
  \ \u05E9\u05DC \u05EA\u05D0\u05E8\u05D9\u05DB\u05D9\u05DD \u05DC\u05E4\u05D5\u05E8\
  \u05DE\u05D8 \u05DE\u05D5\u05D1\u05E0\u05D4 \u05E9\u05D4\u05EA\u05D5\u05DB\u05E0\
  \u05D9\u05EA \u05D9\u05DB\u05D5\u05DC\u05D4 \u05DC\u05EA\u05E4\u05E2\u05DC. \u05D4\
  \u05EA\u05D4\u05DC\u05D9\u05DA \u05D4\u05D6\u05D4 \u05D4\u05D5\u05D0 \u05D9\u05E1\
  \u05D5\u05D3\u05D9 \u05DC\u05D9\u05D9\u05E9\u05D5\u05DE\u05D9\u05DD \u05D4\u05D8\
  \u05D5\u05E4\u05DC\u05D9\u05DD \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD\u2026"
lastmod: '2024-03-13T22:44:39.428822-06:00'
model: gpt-4-0125-preview
summary: "\u05E4\u05D9\u05E2\u05E0\u05D5\u05D7 \u05EA\u05D0\u05E8\u05D9\u05DA \u05DE\
  \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05D1\u05D4\u05D0\u05E1\u05E7\u05DC \u05DB\
  \u05D5\u05DC\u05DC \u05D4\u05DE\u05E8\u05D4 \u05E9\u05DC \u05D9\u05D9\u05E6\u05D5\
  \u05D2\u05D9\u05DD \u05D8\u05E7\u05E1\u05D8\u05D5\u05D0\u05DC\u05D9\u05D9\u05DD\
  \ \u05E9\u05DC \u05EA\u05D0\u05E8\u05D9\u05DB\u05D9\u05DD \u05DC\u05E4\u05D5\u05E8\
  \u05DE\u05D8 \u05DE\u05D5\u05D1\u05E0\u05D4 \u05E9\u05D4\u05EA\u05D5\u05DB\u05E0\
  \u05D9\u05EA \u05D9\u05DB\u05D5\u05DC\u05D4 \u05DC\u05EA\u05E4\u05E2\u05DC."
title: "\u05E4\u05E8\u05E1\u05D5\u05DD \u05EA\u05D0\u05E8\u05D9\u05DA \u05DE\u05DE\
  \u05D7\u05E8\u05D5\u05D6\u05EA"
weight: 30
---

## איך לעשות:
מחוץ לקופסה, האסקל מציע כלים בסיסיים לפיענוח תאריכים, אולם שימוש בספריות כמו `time` לפונקציונליות הליבה ו`date-parse` או `time-parse` לפיענוח גמיש יותר יכול באופן משמעותי לפשט את המשימה.

ראשית, ודא שהספריה `time` זמינה לך; היא לעיתים קרובות כלולה עם GHC, אך אם אתה צריך לציין אותה כתלות, הוסף את `time` לקובץ cabal של הפרויקט שלך או השתמש ב`cabal install time` כדי להתקין אותה ידנית.

```haskell
import Data.Time.Format
import Data.Time.Clock
import System.Locale (defaultTimeLocale)

-- שימוש בספריית time לפיענוח תאריך בפורמט סטנדרטי
parseBasicDate :: String -> Maybe UTCTime
parseBasicDate = parseTimeM True defaultTimeLocale "%Y-%m-%d" 
```

דוגמה לשימוש ולפלט:

```haskell
main :: IO ()
main = print $ parseBasicDate "2023-04-01"

-- פלט: Just 2023-03-31 22:00:00 UTC
```

לתרחישים מורכבים יותר, בהם אתה צריך להתמודד עם מספר פורמטים או לוקליזציות, ספריות צד שלישי כמו `date-parse` יכולות להיות נוחות יותר:

בהנחה שהוספת את `date-parse` לתלויות שלך והתקנת אותה, הנה איך ייתכן שתשתמש בה:

```haskell
import Data.Time.Calendar
import Text.Date.Parse (parseDate)

-- פיענוח מחרוזת תאריך עם הספריית date-parse תומך במספר פורמטים
parseFlexibleDate :: String -> Maybe Day
parseFlexibleDate = parseDate
```

דוגמה לשימוש עם `date-parse`:

```haskell
main :: IO ()
main = print $ parseFlexibleDate "April 1, 2023"

-- פלט: Just 2023-04-01
```

כל דוגמה מדגימה את הגישה היסודית לקחת מחרוזת ולהופכה לאובייקט תאריך שימושי בהאסקל. הבחירה בין שימוש בפונקציות פנימיות של ספריית `time` לבין בחירה בפתרון של צד שלישי כמו `date-parse` תלויה בצרכים הספציפיים של היישום שלך, כמו טווח הפורמטים שאתה צריך להתמודד איתם.
