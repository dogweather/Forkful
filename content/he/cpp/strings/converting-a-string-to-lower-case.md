---
aliases:
- /he/cpp/converting-a-string-to-lower-case/
date: 2024-01-20 17:38:34.010010-07:00
description: "\u05D4\u05DE\u05E8\u05EA \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05DC\
  \u05D0\u05D5\u05EA\u05D9\u05D5\u05EA \u05E7\u05D8\u05E0\u05D5\u05EA \u05D4\u05D9\
  \u05D0 \u05EA\u05D4\u05DC\u05D9\u05DA \u05E9\u05D1\u05D5 \u05DB\u05DC \u05D4\u05D0\
  \u05D5\u05EA\u05D9\u05D5\u05EA \u05D4\u05D2\u05D3\u05D5\u05DC\u05D5\u05EA \u05D1\
  \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05DE\u05E9\u05EA\u05E0\u05D5\u05EA \u05DC\
  \u05D0\u05D5\u05EA\u05D9\u05D5\u05EA \u05E7\u05D8\u05E0\u05D5\u05EA. \u05D6\u05D4\
  \ \u05E0\u05E2\u05E9\u05D4 \u05DC\u05E2\u05D9\u05EA\u05D9\u05DD \u05E7\u05E8\u05D5\
  \u05D1\u05D5\u05EA \u05DB\u05D3\u05D9 \u05DC\u05D4\u05D1\u05D8\u05D9\u05D7 \u05D0\
  \u05D7\u05D9\u05D3\u05D5\u05EA \u05D1\u05D8\u05D9\u05E4\u05D5\u05DC \u05D1\u05D8\
  \u05E7\u05E1\u05D8 \u05D5\u05DC\u05E2\u05E8\u05D5\u05DA\u2026"
lastmod: 2024-02-18 23:08:53.144709
model: gpt-4-1106-preview
summary: "\u05D4\u05DE\u05E8\u05EA \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05DC\u05D0\
  \u05D5\u05EA\u05D9\u05D5\u05EA \u05E7\u05D8\u05E0\u05D5\u05EA \u05D4\u05D9\u05D0\
  \ \u05EA\u05D4\u05DC\u05D9\u05DA \u05E9\u05D1\u05D5 \u05DB\u05DC \u05D4\u05D0\u05D5\
  \u05EA\u05D9\u05D5\u05EA \u05D4\u05D2\u05D3\u05D5\u05DC\u05D5\u05EA \u05D1\u05DE\
  \u05D7\u05E8\u05D5\u05D6\u05EA \u05DE\u05E9\u05EA\u05E0\u05D5\u05EA \u05DC\u05D0\
  \u05D5\u05EA\u05D9\u05D5\u05EA \u05E7\u05D8\u05E0\u05D5\u05EA. \u05D6\u05D4 \u05E0\
  \u05E2\u05E9\u05D4 \u05DC\u05E2\u05D9\u05EA\u05D9\u05DD \u05E7\u05E8\u05D5\u05D1\
  \u05D5\u05EA \u05DB\u05D3\u05D9 \u05DC\u05D4\u05D1\u05D8\u05D9\u05D7 \u05D0\u05D7\
  \u05D9\u05D3\u05D5\u05EA \u05D1\u05D8\u05D9\u05E4\u05D5\u05DC \u05D1\u05D8\u05E7\
  \u05E1\u05D8 \u05D5\u05DC\u05E2\u05E8\u05D5\u05DA\u2026"
title: "\u05D4\u05DE\u05E8\u05EA \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05DC\u05D0\
  \u05D5\u05EA\u05D9\u05D5\u05EA \u05E7\u05D8\u05E0\u05D5\u05EA"
---

{{< edit_this_page >}}

## מה ולמה?
המרת מחרוזת לאותיות קטנות היא תהליך שבו כל האותיות הגדולות במחרוזת משתנות לאותיות קטנות. זה נעשה לעיתים קרובות כדי להבטיח אחידות בטיפול בטקסט ולערוך השוואות מחרוזות ללא תלות ברישיות.

## איך לעשות:
בדוגמה הבאה נשתמש בפונקציה `std::transform` כדי להמיר כל אות במחרוזת לאות קטנה.

```C++
#include <iostream>
#include <algorithm>
#include <string>
#include <cctype> // לשימוש בפונקציה tolower

int main() {
    std::string text = "HeLLo WoRLD!";
    std::transform(text.begin(), text.end(), text.begin(), 
                   [](unsigned char c) -> unsigned char { return std::tolower(c); });

    std::cout << text; // פלט: hello world!
    return 0;
}
```

## מבט עמוק:
היסטורית, המרה לאותיות קטנות התבצעה גם בעזרת לולאות שרצו על כל תו במחרוזת וביצעו השוואות והמרות ידניות. כלי הסטנדרטי `std::transform` הגיע לפשט את התהליך הזה. חלופות נוספות כוללות שימוש בפונקציות כמו `tolower` בצורה ישירה בתוך לולאה או שימוש בספריות שלישיות שמוסיפות יכולות מניפולציה על מחרוזות.

גם כאשר משתמשים ב`std::tolower`, חשוב להעביר את הפרמטר כ-`unsigned char` כדי למנוע בעיות עם תווים שאינם חלק מ-ASCII. עם זאת, כשעובדים עם UTF-8 או מערכת תווים אחרת, עלולות להיות דרישות מיוחדות שצריך לתת להן את הדעת.

## ראה גם:
- Documentation on `std::transform`: https://en.cppreference.com/w/cpp/algorithm/transform
- Documentation on `std::tolower`: https://en.cppreference.com/w/cpp/string/byte/tolower
- C++ reference for `std::string`: https://en.cppreference.com/w/cpp/string/basic_string
- Unicode handling in C++: https://unicode-org.github.io/icu/userguide/cpp/
