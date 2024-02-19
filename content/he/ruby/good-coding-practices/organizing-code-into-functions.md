---
aliases:
- /he/ruby/organizing-code-into-functions/
date: 2024-01-26 01:16:47.849387-07:00
description: "\u05D0\u05E8\u05D2\u05D5\u05DF \u05E7\u05D5\u05D3 \u05DC\u05EA\u05D5\
  \u05DA \u05E4\u05D5\u05E0\u05E7\u05E6\u05D9\u05D5\u05EA \u05DE\u05D7\u05DC\u05E7\
  \ \u05D0\u05EA \u05D4\u05E1\u05E7\u05E8\u05D9\u05E4\u05D8 \u05E9\u05DC\u05DA \u05DC\
  \u05D7\u05EA\u05D9\u05DB\u05D5\u05EA \u05E0\u05D9\u05EA\u05E0\u05D5\u05EA \u05DC\
  \u05E9\u05D9\u05DE\u05D5\u05E9 \u05D7\u05D5\u05D6\u05E8. \u05D4\u05DE\u05D5\u05D8\
  \u05D5 \u05DB\u05D0\u05DF \u05D4\u05D5\u05D0 \u05DC\u05D4\u05E4\u05D5\u05DA \u05D0\
  \u05EA \u05D4\u05E7\u05D5\u05D3 \u05E9\u05DC\u05DA \u05DC\u05E0\u05E7\u05D9, \u05E0\
  \u05D9\u05EA\u05DF \u05DC\u05E0\u05D9\u05D4\u05D5\u05DC \u05D5\u05E4\u05D7\u05D5\
  \u05EA \u05D8\u05E2\u05D5\u05DF \u05DC\u05E9\u05D2\u05D9\u05D0\u05D5\u05EA. \u05E7\
  \u05D5\u05D3 \u05DE\u05D5\u05D3\u05D5\u05DC\u05E8\u05D9\u2026"
lastmod: 2024-02-18 23:08:53.396786
model: gpt-4-0125-preview
summary: "\u05D0\u05E8\u05D2\u05D5\u05DF \u05E7\u05D5\u05D3 \u05DC\u05EA\u05D5\u05DA\
  \ \u05E4\u05D5\u05E0\u05E7\u05E6\u05D9\u05D5\u05EA \u05DE\u05D7\u05DC\u05E7 \u05D0\
  \u05EA \u05D4\u05E1\u05E7\u05E8\u05D9\u05E4\u05D8 \u05E9\u05DC\u05DA \u05DC\u05D7\
  \u05EA\u05D9\u05DB\u05D5\u05EA \u05E0\u05D9\u05EA\u05E0\u05D5\u05EA \u05DC\u05E9\
  \u05D9\u05DE\u05D5\u05E9 \u05D7\u05D5\u05D6\u05E8. \u05D4\u05DE\u05D5\u05D8\u05D5\
  \ \u05DB\u05D0\u05DF \u05D4\u05D5\u05D0 \u05DC\u05D4\u05E4\u05D5\u05DA \u05D0\u05EA\
  \ \u05D4\u05E7\u05D5\u05D3 \u05E9\u05DC\u05DA \u05DC\u05E0\u05E7\u05D9, \u05E0\u05D9\
  \u05EA\u05DF \u05DC\u05E0\u05D9\u05D4\u05D5\u05DC \u05D5\u05E4\u05D7\u05D5\u05EA\
  \ \u05D8\u05E2\u05D5\u05DF \u05DC\u05E9\u05D2\u05D9\u05D0\u05D5\u05EA. \u05E7\u05D5\
  \u05D3 \u05DE\u05D5\u05D3\u05D5\u05DC\u05E8\u05D9\u2026"
title: "\u05D0\u05E8\u05D2\u05D5\u05DF \u05E7\u05D5\u05D3 \u05DC\u05EA\u05D5\u05DA\
  \ \u05E4\u05D5\u05E0\u05E7\u05E6\u05D9\u05D5\u05EA"
---

{{< edit_this_page >}}

## מה ולמה?
ארגון קוד לתוך פונקציות מחלק את הסקריפט שלך לחתיכות ניתנות לשימוש חוזר. המוטו כאן הוא להפוך את הקוד שלך לנקי, ניתן לניהול ופחות טעון לשגיאות. קוד מודולרי זה טוב מכיוון שהוא חוסך לך זמן, שומר על שפיותך, ומפשט את האיתור ובדיקות יחידה.

## איך לעשות:
דמיין שאתה כותב סקריפט מהיר לברך משתמשים:

```Ruby
def greet(name)
  "Hello, #{name}!"
end

puts greet("Alice")   # פלט: Hello, Alice!
puts greet("Bob")     # פלט: Hello, Bob!
```

או אולי אתה מחשב את שטח המעגל:

```Ruby
def circle_area(radius)
  Math::PI * radius ** 2
end

puts circle_area(5)   # פלט: 78.53981633974483
```

נקי וקל יותר להתמודד, נכון?

## צלילה עמוקה
המושג של פונקציות, ידוע גם כשיטות בRuby, אינו חדש – הוא קדום כמו התכנות עצמו. חוזרים אחורה לשנות ה-50, תת-תכניות, כפי שהיו מוכרות, הוצגו כדי להפחית חפיפה.

אלטרנטיבות? בטח, יש לך קוד inline, או אפשר ללכת על תכנות מונחה עצמים עם classes וobjects, או אפילו פונקציונלי עם lambdas וprocs. אבל הפונקציות הן לחם וחמאה של קוד מסודר. רוצה ביצועים? משתנים מקומיים בפונקציות הם מהירים ופונקציות יכולות להחזיר ערכים מיד עם `return`.

בפן היישום, ניתן להגדיר פונקציה עם `def` ולסיים אותה עם `end`. ניתן להגדיר פרמטרים ברירת מחדל, להשתמש באופרטורים splat עבור פונקציות וריאדיות, ועוד. פונקציות יכולות להיות פשוטות או מורכבות כפי שתרצה הלב.

## ראה גם
- [תיעוד השיטה של Ruby](https://ruby-doc.org/core-2.7.0/Method.html)
- [ללמוד לתכנת מאת כריס פיין](https://pine.fm/LearnToProgram/)
- [עיצוב מעשי מונחה-עצמים בRuby מאת סנדי מץ](https://www.poodr.com/)
