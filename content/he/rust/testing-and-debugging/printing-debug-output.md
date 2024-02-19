---
aliases:
- /he/rust/printing-debug-output/
date: 2024-01-20 17:53:25.872402-07:00
description: "\u05D3\u05D9\u05D1\u05D0\u05D2 (Debug) \u05D4\u05D5\u05D0 \u05D4\u05D3\
  \u05E4\u05E1\u05EA \u05D1\u05D3\u05D9\u05E7\u05D5\u05EA \u05D1\u05E7\u05D5\u05D3\
  \ \u05DB\u05D3\u05D9 \u05DC\u05D4\u05D1\u05D9\u05DF \u05DE\u05D4 \u05E7\u05D5\u05E8\
  \u05D4 \u05D1\u05DE\u05D4\u05DC\u05DA \u05E8\u05D9\u05E6\u05EA \u05D4\u05EA\u05D5\
  \u05DB\u05E0\u05D9\u05EA. \u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05E2\u05D5\
  \u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9 \u05DC\u05D0\u05EA\u05E8\
  \ \u05D1\u05D0\u05D2\u05D9\u05DD, \u05DC\u05E4\u05E7\u05D7 \u05E2\u05DC \u05D6\u05E8\
  \u05D9\u05DE\u05EA \u05D4\u05EA\u05DB\u05E0\u05D9\u05EA \u05D5\u05DC\u05D1\u05D3\
  \u05D5\u05E7 \u05EA\u05D5\u05E6\u05D0\u05D5\u05EA \u05E9\u05DC \u05E4\u05D5\u05E0\
  \u05E7\u05E6\u05D9\u05D5\u05EA."
lastmod: 2024-02-18 23:08:52.617654
model: gpt-4-1106-preview
summary: "\u05D3\u05D9\u05D1\u05D0\u05D2 (Debug) \u05D4\u05D5\u05D0 \u05D4\u05D3\u05E4\
  \u05E1\u05EA \u05D1\u05D3\u05D9\u05E7\u05D5\u05EA \u05D1\u05E7\u05D5\u05D3 \u05DB\
  \u05D3\u05D9 \u05DC\u05D4\u05D1\u05D9\u05DF \u05DE\u05D4 \u05E7\u05D5\u05E8\u05D4\
  \ \u05D1\u05DE\u05D4\u05DC\u05DA \u05E8\u05D9\u05E6\u05EA \u05D4\u05EA\u05D5\u05DB\
  \u05E0\u05D9\u05EA. \u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05E2\u05D5\u05E9\
  \u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9 \u05DC\u05D0\u05EA\u05E8 \u05D1\
  \u05D0\u05D2\u05D9\u05DD, \u05DC\u05E4\u05E7\u05D7 \u05E2\u05DC \u05D6\u05E8\u05D9\
  \u05DE\u05EA \u05D4\u05EA\u05DB\u05E0\u05D9\u05EA \u05D5\u05DC\u05D1\u05D3\u05D5\
  \u05E7 \u05EA\u05D5\u05E6\u05D0\u05D5\u05EA \u05E9\u05DC \u05E4\u05D5\u05E0\u05E7\
  \u05E6\u05D9\u05D5\u05EA."
title: "\u05D4\u05D3\u05E4\u05E1\u05EA \u05E4\u05DC\u05D8 \u05DC\u05E0\u05D9\u05E4\
  \u05D5\u05D9 \u05D1\u05D0\u05D2\u05D9\u05DD"
---

{{< edit_this_page >}}

## מה ולמה?
דיבאג (Debug) הוא הדפסת בדיקות בקוד כדי להבין מה קורה במהלך ריצת התוכנית. מתכנתים עושים זאת כדי לאתר באגים, לפקח על זרימת התכנית ולבדוק תוצאות של פונקציות.

## איך עושים את זה:
ב-Rust להדפסת דיבאג נעשה שימוש במאקרו `println!` או `eprintln!` להדפסה לפלט השגיאה.
```Rust
fn main() {
    let var = vec![1, 2, 3];
    println!("Debug: {:?}", var);
}
```
פלט לדוגמא:
```
Debug: [1, 2, 3]
```

כדי להשיג פלט יותר מורכב, נשתמש ב-`{:#?}` במקום ב-`{:?}`.
```Rust
fn main() {
    let var = vec![1, 2, 3];
    println!("Debug pretty-print: {:#?}", var);
}
```
פלט לדוגמא:
```
Debug pretty-print:
[
    1,
    2,
    3,
]
```

## הבט העמוק יותר
בעבר, לפני שפות כמו Rust קיימות, מתכנתים השתמשו ברשומות הדפסה או כתיבה לקובץ כדי לקבל משוב מן התוכנית. ב-Rust, הסטנדרט הוא להשתמש במאקרוס של הדפסה לפלט שבהם אפשר להדפיס ערכים או מבני נתונים שהם חלק מפיתרון הבעיה.

התכונה `Debug` דורשת שהטיפוס ייישם או יגדיר את תוכנית ההדפסה שלו. אלטרנטיבת הדפסה היא השימוש במאקרו `log!` בשילוב עם ספריות רישום (logging libraries) שמאפשרות לקבוע רמות דיבאג שונות.

## ראה גם
* מדריך התחלתי ל-Rust: https://www.rust-lang.org/learn/get-started
* מדריך למאקרוס `println!` ו`format!`: https://doc.rust-lang.org/std/fmt/
* ספריית רישום log: https://crates.io/crates/log
* ספריית env_logger (שילוב נפוץ עם log): https://crates.io/crates/env_logger
