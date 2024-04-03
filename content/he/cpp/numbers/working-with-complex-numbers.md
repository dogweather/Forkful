---
date: 2024-01-26 04:39:03.929232-07:00
description: "\u05DE\u05E1\u05E4\u05E8\u05D9\u05DD \u05DE\u05E8\u05D5\u05DB\u05D1\u05D9\
  \u05DD \u05DE\u05E8\u05D7\u05D9\u05D1\u05D9\u05DD \u05D0\u05EA \u05D4\u05DE\u05E1\
  \u05E4\u05E8\u05D9\u05DD \u05D4\u05DE\u05DE\u05E9\u05D9\u05D9\u05DD \u05E2\u05DC\
  \ \u05D9\u05D3\u05D9 \u05D4\u05D5\u05E1\u05E4\u05EA \u05D9\u05D7\u05D9\u05D3\u05D4\
  \ \u05DE\u05D3\u05D5\u05DE\u05D4, \u05E9\u05DE\u05D9\u05D5\u05E6\u05D2\u05EA \u05DB\
  -'i', \u05DB\u05D0\u05E9\u05E8 i^2 = -1. \u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\u05DD\
  \ \u05DE\u05E9\u05EA\u05DE\u05E9\u05D9\u05DD \u05D1\u05D4\u05DD \u05DC\u05E1\u05D9\
  \u05DE\u05D5\u05DC\u05E6\u05D9\u05D5\u05EA, \u05E2\u05D9\u05D1\u05D5\u05D3 \u05D0\
  \u05D5\u05EA\u05D5\u05EA \u05D5\u05E4\u05EA\u05E8\u05D5\u05DF \u05D1\u05E2\u05D9\
  \u05D5\u05EA\u2026"
lastmod: '2024-03-13T22:44:39.825534-06:00'
model: gpt-4-0125-preview
summary: "\u05DE\u05E1\u05E4\u05E8\u05D9\u05DD \u05DE\u05E8\u05D5\u05DB\u05D1\u05D9\
  \u05DD \u05DE\u05E8\u05D7\u05D9\u05D1\u05D9\u05DD \u05D0\u05EA \u05D4\u05DE\u05E1\
  \u05E4\u05E8\u05D9\u05DD \u05D4\u05DE\u05DE\u05E9\u05D9\u05D9\u05DD \u05E2\u05DC\
  \ \u05D9\u05D3\u05D9 \u05D4\u05D5\u05E1\u05E4\u05EA \u05D9\u05D7\u05D9\u05D3\u05D4\
  \ \u05DE\u05D3\u05D5\u05DE\u05D4, \u05E9\u05DE\u05D9\u05D5\u05E6\u05D2\u05EA \u05DB\
  -'i', \u05DB\u05D0\u05E9\u05E8 i^2 = -1."
title: "\u05E2\u05D1\u05D5\u05D3\u05D4 \u05E2\u05DD \u05DE\u05E1\u05E4\u05E8\u05D9\
  \u05DD \u05DE\u05E8\u05D5\u05DB\u05D1\u05D9\u05DD"
weight: 14
---

## איך לעבוד עם זה:
ב-C++ קיימת ספרייה מובנית `<complex>` שמקלה על העבודה עם מספרים מרוכבים. הנה הצצה מהירה:

```cpp
#include <iostream>
#include <complex>

int main() {
    std::complex<double> num1(2.0, 3.0); // יוצר מספר מרוכב (2 + 3i)
    std::complex<double> num2(3.0, 4.0); // מספר מרוכב נוסף (3 + 4i)

    // חיבור
    std::complex<double> result = num1 + num2;
    std::cout << "תוצאת החיבור: " << result << std::endl; // (5 + 7i)

    // כפל
    result = num1 * num2;
    std::cout << "תוצאת הכפל: " << result << std::endl; // (-6 + 17i)

    // מצורע
    result = std::conj(num1);
    std::cout << "מצורע של num1: " << result << std::endl; // (2 - 3i)
    
    return 0;
}
```

## צלילה עמוקה
למספרים מרוכבים יש היסטוריה עשירה, המופיעה לראשונה בפתרונות למשוואות מעלה שלישית במאה ה-16. הם חיוניים במגוון תחומים, לא רק בתכנות. במדעי המחשב, מספרים מרוכבים עוזרים באלגוריתמים שדורשים מרחב מספרי דו-ממדי, כמו ההמרה המהירה של פורייה (FFT).

למרות שספריית ה-`<complex>` של C++ היא סטנדרטית, קיימות אלטרנטיבות בשפות אחרות, כמו סוג הנתונים `complex` בפייתון או ספריות המתמטיקה של ג'אווהסקריפט. עצמה ספריית ה-`<complex>` מספקת פונקציונליות מקיפה, כולל פעולות טריגונומטריות, אקספוננציאליות, ולוגריתמיות המותאמות למספרים מרוכבים.

כאשר מתכנתים נתונים אלה, מפתח להבין את המתמטיקה שמאחורי הקלעים כדי למנוע אי-דיוקים ולהבין פעולות כמו הצורב המרוכב, שפונה את סימן החלק המדומה, או המשמעויות של נוסחת אוילר הקושרת בין אקספוננציאליים מרוכבים לפונקציות טריגונומטריות.

## ראו גם
- תיעוד של ספריית התבניות הסטנדרטיות של C++: https://en.cppreference.com/w/cpp/header/complex
- צלילה מתמטית עמוקה יותר לתוך מספרים מרוכבים: https://mathworld.wolfram.com/ComplexNumber.html
- לוויזואליזציה, ספריית הפייתון Matplotlib יכולה לשרטט מספרים מרוכבים: https://matplotlib.org/
