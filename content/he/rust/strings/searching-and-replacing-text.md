---
date: 2024-01-20 17:58:54.176674-07:00
description: "\u05DC\u05D7\u05E4\u05E9 \u05D5\u05DC\u05D4\u05D7\u05DC\u05D9\u05E3\
  \ \u05D8\u05E7\u05E1\u05D8 \u05D6\u05D4 \u05E4\u05E2\u05D5\u05DC\u05D4 \u05E9\u05DE\
  \u05D0\u05E4\u05E9\u05E8\u05EA \u05DC\u05DE\u05E6\u05D5\u05D0 \u05DE\u05D7\u05E8\
  \u05D5\u05D6\u05D5\u05EA \u05D1\u05EA\u05D5\u05DA \u05D8\u05E7\u05E1\u05D8 \u05D5\
  \u05DC\u05D4\u05D7\u05DC\u05D9\u05E4\u05DD \u05D1\u05D0\u05D7\u05E8\u05D9\u05DD\
  . \u05EA\u05DB\u05E0\u05D5\u05EA\u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D0\
  \u05EA \u05D6\u05D4 \u05D1\u05E9\u05D1\u05D9\u05DC \u05DC\u05E2\u05D3\u05DB\u05DF\
  \ \u05E7\u05D5\u05D3, \u05DC\u05EA\u05E7\u05DF \u05E9\u05D2\u05D9\u05D0\u05D5\u05EA\
  , \u05D0\u05D5 \u05DC\u05E9\u05E0\u05D5\u05EA \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD\
  \ \u05D1\u05E4\u05E8\u05D5\u05D9\u05E7\u05D8."
lastmod: '2024-03-13T22:44:38.962784-06:00'
model: gpt-4-1106-preview
summary: "\u05DC\u05D7\u05E4\u05E9 \u05D5\u05DC\u05D4\u05D7\u05DC\u05D9\u05E3 \u05D8\
  \u05E7\u05E1\u05D8 \u05D6\u05D4 \u05E4\u05E2\u05D5\u05DC\u05D4 \u05E9\u05DE\u05D0\
  \u05E4\u05E9\u05E8\u05EA \u05DC\u05DE\u05E6\u05D5\u05D0 \u05DE\u05D7\u05E8\u05D5\
  \u05D6\u05D5\u05EA \u05D1\u05EA\u05D5\u05DA \u05D8\u05E7\u05E1\u05D8 \u05D5\u05DC\
  \u05D4\u05D7\u05DC\u05D9\u05E4\u05DD \u05D1\u05D0\u05D7\u05E8\u05D9\u05DD."
title: "\u05D7\u05D9\u05E4\u05D5\u05E9 \u05D5\u05D4\u05D7\u05DC\u05E4\u05EA \u05D8\
  \u05E7\u05E1\u05D8"
weight: 10
---

## How to: (איך לעשות:)
```Rust
fn main() {
    let text = "Hello, world! Programming in Rust is fun.";
    let search = "world";
    let replace_with = "there";

    let replaced_text = text.replace(search, replace_with);
    println!("{}", replaced_text);
}
```
פלט:
```
Hello, there! Programming in Rust is fun.
```

## Deep Dive (צלילה עמוקה)
בעולם התוכנה, פעולת החיפוש והחלפה הייתה חלק מעורכי טקסט מהימים הראשונים של תכנות. זה מכשיר חזק שיכול לחסוך זמן רב ולמנוע שגיאות. בראסט, `str::replace` היא פונקציה פשוטה וישירה לשימוש זה. חלופות כוללות ביטויים רגולריים עם crate `regex` לחיפושים מורכבים יותר, וגיימן למניפולציה של טקסט עם `str::split` ואיטרטורים. פנימית, פעולת החיפוש והחלפה מתבצעת על ידי סריקה של המחרוזת ובנייה מחדש של מחרוזת עם הערכים החדשים.

## See Also (ראה גם)
- [Rust std::str documentation](https://doc.rust-lang.org/std/str/)
- [Rust by Example: Strings](https://doc.rust-lang.org/rust-by-example/std/str.html)
- [`regex` crate documentation](https://docs.rs/regex/latest/regex/)
