---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:53:45.235110-07:00
description: "\u05D7\u05D9\u05DC\u05D5\u05E5 \u05EA\u05EA-\u05DE\u05D7\u05E8\u05D5\
  \u05D6\u05D5\u05EA \u05DB\u05D5\u05DC\u05DC \u05DC\u05E7\u05D9\u05D7\u05EA \u05D7\
  \u05DC\u05E7 \u05DE\u05DE\u05D7\u05E8\u05D5\u05D6\u05EA - \u05D1\u05E2\u05E6\u05DD\
  \ \u05D9\u05E6\u05D9\u05E8\u05EA \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05D7\u05D3\
  \u05E9\u05D4 \u05DE\u05EA\u05D5\u05DA \u05D7\u05DC\u05E7 \u05DE\u05DE\u05D7\u05E8\
  \u05D5\u05D6\u05EA \u05E7\u05D9\u05D9\u05DE\u05EA. \u05DE\u05EA\u05DB\u05E0\u05EA\
  \u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DE\u05DE\u05D2\
  \u05D5\u05D5\u05DF \u05E1\u05D9\u05D1\u05D5\u05EA, \u05DB\u05D5\u05DC\u05DC \u05E4\
  \u05D9\u05E8\u05D5\u05E7 \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD, \u05E0\u05D9\u05D4\
  \u05D5\u05DC \u05D8\u05E7\u05E1\u05D8\u2026"
lastmod: '2024-03-13T22:44:38.545930-06:00'
model: gpt-4-0125-preview
summary: "\u05D7\u05D9\u05DC\u05D5\u05E5 \u05EA\u05EA-\u05DE\u05D7\u05E8\u05D5\u05D6\
  \u05D5\u05EA \u05DB\u05D5\u05DC\u05DC \u05DC\u05E7\u05D9\u05D7\u05EA \u05D7\u05DC\
  \u05E7 \u05DE\u05DE\u05D7\u05E8\u05D5\u05D6\u05EA - \u05D1\u05E2\u05E6\u05DD \u05D9\
  \u05E6\u05D9\u05E8\u05EA \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05D7\u05D3\u05E9\
  \u05D4 \u05DE\u05EA\u05D5\u05DA \u05D7\u05DC\u05E7 \u05DE\u05DE\u05D7\u05E8\u05D5\
  \u05D6\u05EA \u05E7\u05D9\u05D9\u05DE\u05EA."
title: "\u05D7\u05D9\u05DC\u05D5\u05E5 \u05EA\u05EA-\u05DE\u05D7\u05E8\u05D5\u05D6\
  \u05D5\u05EA"
weight: 6
---

## איך לעשות:
ב-Google Apps Script, המבוסס על JavaScript מודרני, ניתן להשיג חילוץ תת-מחרוזות באמצעות שיטות שונות, כולל `substring()`, `substr()`, ו-`slice()`. כל אחת מהן מציעה ניואנסים משלה, אך כולן שואפות להשיג את המטרה של חלץ תווים מצויינים ממחרוזת.

```javascript
// דוגמה באמצעות substring()
var str = "Hello, world!";
var result = str.substring(0, 5);
console.log(result); // פלט: Hello

// דוגמה באמצעות substr()
var resultSubstr = str.substr(7, 5);
console.log(resultSubstr); // פלט: world

// דוגמה באמצעות slice()
var resultSlice = str.slice(-6);
console.log(resultSlice); // פלט: world!
```

כל שיטה מקבלת שני ארגומנטים: מיקום התחלה ומיקום סיום, למעט `slice()` שיכול לקבל אינדקסים שליליים להתחלה מהסוף, או מספר התווים לחלץ. כדאי לשים לב שהמחרוזת המקורית נשארת ללא שינוי לאחר מבצעים אלו, כיוון שהם מחזירים ערכי מחרוזת חדשים.

## עיון מעמיק
באופן היסטורי, שיטות JavaScript לחילוץ תת-מחרוזות היו מקור לבלבול בשל שמותיהן ופונקציונליותיהן הדומה. עם זאת, ב-Google Apps Script וב-JavaScript מודרני, `substring()` ו-`slice()` הם הנפוצים ביותר לשימוש, עם `substr()` שנחשב למיושן. זה חשוב לזכור למי שכותב קוד שיחזיק מעמד לעתיד.

ההבדל העיקרי בין `substring()` ל-`slice()` הוא איך שהן מתמודדות עם אינדקסים שליליים; `substring()` מתייחסת לאינדקסים שליליים כאילו הם 0, בעוד ש-`slice()` יכולה לקבל אינדקס שלילי כדי להתחיל את החילוץ מסוף המחרוזת. זה הופך את `slice()` למאוד שימושי במקרים שאורך המחרוזת אינו ידוע בוודאות או בעת הצורך לחלץ מהסוף.

כשמחליטים איזו שיטה להשתמש לחילוץ תת-מחרוזות, הבחירה לעיתים קרובות תלויה בדרישות הספציפיות של הפעולה (למשל, האם טיפול באינדקסים שליליים מועיל) ובתקנות הכתיבה האישיים או של הצוות. אף שאין "השיטה הטובה ביותר" שמתאימה לכולם, הבנה של ההבדלים העדינים וההשלכות על הביצועים יכולה לעזור לקבל החלטה מושכלת.
