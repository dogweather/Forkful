---
date: 2024-01-26 01:16:56.496769-07:00
description: "\u05D0\u05E8\u05D2\u05D5\u05DF \u05E7\u05D5\u05D3 \u05DC\u05EA\u05D5\
  \u05DA \u05E4\u05D5\u05E0\u05E7\u05E6\u05D9\u05D5\u05EA \u05E2\u05D5\u05E1\u05E7\
  \ \u05D1\u05E9\u05D1\u05D9\u05E8\u05EA \u05D4\u05EA\u05D5\u05DB\u05E0\u05D9\u05EA\
  \ \u05E9\u05DC\u05DA \u05DC\u05D7\u05EA\u05D9\u05DB\u05D5\u05EA \u05DE\u05D5\u05D3\
  \u05D5\u05DC\u05E8\u05D9\u05D5\u05EA \u05D5\u05E0\u05D9\u05EA\u05E0\u05D5\u05EA\
  \ \u05DC\u05E9\u05D9\u05DE\u05D5\u05E9 \u05D7\u05D5\u05D6\u05E8 \u05D4\u05DE\u05D6\
  \u05D5\u05D4\u05D5\u05EA \u05E2\u05DC \u05D9\u05D3\u05D9 \u05E9\u05DD. \u05D0\u05E0\
  \u05D5 \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05E2\u05DC \u05DE\u05E0\
  \u05EA \u05DC\u05D4\u05E4\u05D5\u05DA \u05D0\u05EA \u05D4\u05E7\u05D5\u05D3 \u05E9\
  \u05DC\u05E0\u05D5 \u05DC\u05E0\u05E7\u05D9\u2026"
lastmod: '2024-03-13T22:44:38.996821-06:00'
model: gpt-4-0125-preview
summary: "\u05D0\u05E8\u05D2\u05D5\u05DF \u05E7\u05D5\u05D3 \u05DC\u05EA\u05D5\u05DA\
  \ \u05E4\u05D5\u05E0\u05E7\u05E6\u05D9\u05D5\u05EA \u05E2\u05D5\u05E1\u05E7 \u05D1\
  \u05E9\u05D1\u05D9\u05E8\u05EA \u05D4\u05EA\u05D5\u05DB\u05E0\u05D9\u05EA \u05E9\
  \u05DC\u05DA \u05DC\u05D7\u05EA\u05D9\u05DB\u05D5\u05EA \u05DE\u05D5\u05D3\u05D5\
  \u05DC\u05E8\u05D9\u05D5\u05EA \u05D5\u05E0\u05D9\u05EA\u05E0\u05D5\u05EA \u05DC\
  \u05E9\u05D9\u05DE\u05D5\u05E9 \u05D7\u05D5\u05D6\u05E8 \u05D4\u05DE\u05D6\u05D5\
  \u05D4\u05D5\u05EA \u05E2\u05DC \u05D9\u05D3\u05D9 \u05E9\u05DD."
title: "\u05D0\u05E8\u05D2\u05D5\u05DF \u05E7\u05D5\u05D3 \u05DC\u05EA\u05D5\u05DA\
  \ \u05E4\u05D5\u05E0\u05E7\u05E6\u05D9\u05D5\u05EA"
weight: 18
---

## איך לעשות:
נניח שיש לך קוד שמחשב את שטח המעגל מספר פעמים. במקום לחזור על הנוסחה, אתה מכניס אותה לתוך פונקציה.

```Rust
fn calculate_circle_area(radius: f64) -> f64 {
    std::f64::consts::PI * radius.powi(2)
}

fn main() {
    let radius = 5.0;
    let area = calculate_circle_area(radius);
    println!("שטח המעגל הוא: {}", area);
}
```

פלט:

```
שטח המעגל הוא: 78.53981633974483
```

## צלילה עמוקה
בהיסטוריה, פונקציות הגיעו מהמתמטיקה, שם הן ממפות קלטים לפלטים. בתכנות, הן קיימות כבר מימי האסמבלי, אף על פי שקראנו להן 'תת-פרוצדורות'. פונקציות ב-Rust יכולות להחזיר ערכים ואף פונקציות אחרות בזכות פונקציות מדרגה ראשונה וסגירות.

אלטרנטיבות? קוד מוטמע או מקרוסים, אך הם מבולגנים עבור לוגיקה מורכבת. עצמים עם מתודות הם דרך נוספת לארגן פונקציונליות, טעם שונה מאשר פונקציות עצמאיות.

היישום ב-Rust הוא די ישיר. פונקציות מצהירות על סוגי הפרמטרים וסוג ההחזרה שלהן. הן משתמשות ב-'snake case' לשמות לפי מסורת. יש לך את הפונקציות הציבוריות (`pub fn`) לשימוש מחוץ למודול ואת הפרטיות לשימוש פנימי. ול-Rust יש תכונה מגניבה שבה אינך זקוק למילת המפתח `return` עבור הביטוי האחרון בפונקציה.

## ראה גם
בדוק את אלו למידע נוסף:
- ספר השפה Rust: [פונקציות](https://doc.rust-lang.org/book/ch03-03-how-functions-work.html)
- Rust לפי דוגמא על [פונקציות](https://doc.rust-lang.org/rust-by-example/fn.html)
