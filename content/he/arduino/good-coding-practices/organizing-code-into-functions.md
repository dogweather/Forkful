---
date: 2024-01-26 01:09:47.792663-07:00
description: "\u05D0\u05E8\u05D2\u05D5\u05DF \u05E7\u05D5\u05D3 \u05DC\u05EA\u05D5\
  \u05DA \u05E4\u05D5\u05E0\u05E7\u05E6\u05D9\u05D5\u05EA \u05E4\u05D9\u05E8\u05D5\
  \u05E9\u05D5 \u05E4\u05D9\u05E6\u05D5\u05DC \u05D4\u05E7\u05D5\u05D3 \u05DC\u05D1\
  \u05DC\u05D5\u05E7\u05D9\u05DD \u05E9\u05D9\u05DE\u05D5\u05E9\u05D9\u05D9\u05DD\
  \ \u05DE\u05D7\u05D5\u05D3\u05E9, \u05DB\u05DC \u05D1\u05DC\u05D5\u05E7 \u05D0\u05D7\
  \u05E8\u05D0\u05D9 \u05E2\u05DC \u05E4\u05E2\u05D5\u05DC\u05D4 \u05E1\u05E4\u05E6\
  \u05D9\u05E4\u05D9\u05EA. \u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05E2\u05D5\
  \u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9 \u05DC\u05D4\u05E4\u05D5\
  \u05DA \u05D0\u05EA \u05D4\u05E7\u05D5\u05D3 \u05DC\u05E7\u05E8\u05D9\u05D0 \u05D9\
  \u05D5\u05EA\u05E8, \u05DC\u05E0\u05E4\u05D5\u05EA\u2026"
lastmod: '2024-03-13T22:44:39.775742-06:00'
model: gpt-4-1106-preview
summary: "\u05D0\u05E8\u05D2\u05D5\u05DF \u05E7\u05D5\u05D3 \u05DC\u05EA\u05D5\u05DA\
  \ \u05E4\u05D5\u05E0\u05E7\u05E6\u05D9\u05D5\u05EA \u05E4\u05D9\u05E8\u05D5\u05E9\
  \u05D5 \u05E4\u05D9\u05E6\u05D5\u05DC \u05D4\u05E7\u05D5\u05D3 \u05DC\u05D1\u05DC\
  \u05D5\u05E7\u05D9\u05DD \u05E9\u05D9\u05DE\u05D5\u05E9\u05D9\u05D9\u05DD \u05DE\
  \u05D7\u05D5\u05D3\u05E9, \u05DB\u05DC \u05D1\u05DC\u05D5\u05E7 \u05D0\u05D7\u05E8\
  \u05D0\u05D9 \u05E2\u05DC \u05E4\u05E2\u05D5\u05DC\u05D4 \u05E1\u05E4\u05E6\u05D9\
  \u05E4\u05D9\u05EA."
title: "\u05E1\u05D9\u05D3\u05D5\u05E8 \u05E7\u05D5\u05D3 \u05DC\u05EA\u05D5\u05DA\
  \ \u05E4\u05D5\u05E0\u05E7\u05E6\u05D9\u05D5\u05EA"
weight: 18
---

## איך לעשות:
דמיינו שאתם רוצים להבהב נורית LED. בלי פונקציות, הלולאת `loop` שלכם היא גוש מבולגן. עם פונקציות, היא מסודרת. הנה איך:

```Arduino
const int LED_PIN = 13;

void setup() {
  pinMode(LED_PIN, OUTPUT);
}

void loop() {
  blinkLED(500); // מהבהב את ה-LED כל 500 מילי-שניות
}

// פונקציה להבהוב LED
void blinkLED(int delayTime) {
  digitalWrite(LED_PIN, HIGH);
  delay(delayTime);
  digitalWrite(LED_PIN, LOW);
  delay(delayTime);
}
```

תוצאה דוגמה: ה-LED שלכם מהבהב בשמחה, ומטרת הקוד ברורה במבט.

## צלילה לעומק
לפני פונקציות, תיכנות היה טיול רציף על הכביש; ראיתם כל גומה בדרך מההתחלה ועד הסוף. אחרי פונקציות, זה יותר כמו לדלג בין טיסות - אתם קופצים לחלקים החשובים. בהיסטוריה, תת-פרוצדורות (תת-פונקציות מוקדמות) היו מהפיכה בתחום התיכנות, אשר איפשרו למתכנתים להימנע מחזרה על עצמם – זהו עיקרון DRY, Don't Repeat Yourself (אל תחזור על עצמך). אלטרנטיבות לפונקציות עשויות לכלול מאקרוים או שימוש במחלקות לתכנות מונחה עצמים (OOP). הפרטים הקטנים? כאשר אתם מגדירים פונקציה, אתם נותנים למהדר הקוד מפת תוכנית לביצוע משימה. עם Arduino, לרוב אתם מגדירים פונקציות void שמשמשות כפקודות פשוטות למיקרו-בקר, אך פונקציות יכולות גם להחזיר ערכים, ועל כן הן יותר גמישות.

## ראה גם
למידע נוסף על פונקציות, עיינו בקישורים הבאים:

- המדריך הרשמי של Arduino לפונקציות: https://www.arduino.cc/reference/en/language/functions/
- למידע נוסף על עיקרון DRY: https://en.wikipedia.org/wiki/Don%27t_repeat_yourself
- חידון מחודש על היסטוריה של תת-פרוצדורות: https://en.wikipedia.org/wiki/Subroutine
