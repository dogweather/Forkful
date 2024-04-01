---
date: 2024-01-26 04:09:34.633096-07:00
description: "\u05E9\u05D9\u05DE\u05D5\u05E9 \u05D1\u05D3\u05D9\u05D1\u05D0\u05D2\u05E8\
  \ (\u05DE\u05E0\u05E4\u05D4 \u05E9\u05D2\u05D9\u05D0\u05D5\u05EA) \u05E4\u05D9\u05E8\
  \u05D5\u05E9\u05D5 \u05E9\u05DC\u05D9\u05D8\u05D4 \u05D1\u05DB\u05DC\u05D9\u05DD\
  \ \u05DE\u05D9\u05D5\u05D7\u05D3\u05D9\u05DD \u05E9\u05DE\u05D0\u05E4\u05E9\u05E8\
  \u05D9\u05DD \u05DC\u05DA \u05DC\u05E6\u05E6\u05EA \u05DE\u05EA\u05D7\u05EA \u05DC\
  \u05DE\u05DB\u05E1\u05D4 \u05E9\u05DC \u05D4\u05E7\u05D5\u05D3 \u05E9\u05DC\u05DA\
  , \u05DC\u05E6\u05E4\u05D5\u05EA \u05D1\u05D5 \u05DE\u05EA\u05D1\u05E6\u05E2 \u05E6\
  \u05E2\u05D3 \u05D0\u05D7\u05E8 \u05E6\u05E2\u05D3. \u05DE\u05EA\u05DB\u05E0\u05EA\
  \u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9\
  \ \u05DC\u05D3\u05D7\u05D5\u05E1\u2026"
lastmod: '2024-03-13T22:44:39.982293-06:00'
model: gpt-4-0125-preview
summary: "\u05E9\u05D9\u05DE\u05D5\u05E9 \u05D1\u05D3\u05D9\u05D1\u05D0\u05D2\u05E8\
  \ (\u05DE\u05E0\u05E4\u05D4 \u05E9\u05D2\u05D9\u05D0\u05D5\u05EA) \u05E4\u05D9\u05E8\
  \u05D5\u05E9\u05D5 \u05E9\u05DC\u05D9\u05D8\u05D4 \u05D1\u05DB\u05DC\u05D9\u05DD\
  \ \u05DE\u05D9\u05D5\u05D7\u05D3\u05D9\u05DD \u05E9\u05DE\u05D0\u05E4\u05E9\u05E8\
  \u05D9\u05DD \u05DC\u05DA \u05DC\u05E6\u05E6\u05EA \u05DE\u05EA\u05D7\u05EA \u05DC\
  \u05DE\u05DB\u05E1\u05D4 \u05E9\u05DC \u05D4\u05E7\u05D5\u05D3 \u05E9\u05DC\u05DA\
  , \u05DC\u05E6\u05E4\u05D5\u05EA \u05D1\u05D5 \u05DE\u05EA\u05D1\u05E6\u05E2 \u05E6\
  \u05E2\u05D3 \u05D0\u05D7\u05E8 \u05E6\u05E2\u05D3. \u05DE\u05EA\u05DB\u05E0\u05EA\
  \u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9\
  \ \u05DC\u05D3\u05D7\u05D5\u05E1\u2026"
title: "\u05E9\u05D9\u05DE\u05D5\u05E9 \u05D1\u05D3\u05D9\u05D1\u05D0\u05D2\u05E8"
---

## איך לעשות:
הנה קטע קוד ב-JavaScript שאינו נהגה כצפוי:

```javascript
function buggyMultiply(a, b) {
    return a + b; // אופס! זה אמור להיות כפל, לא חיבור.
}

let result = buggyMultiply(5, 3);
console.log('Result:', result);
```

הפלט אינו נכון:
```
Result: 8
```

בואו נבצע ניפוי באגים ב- Chrome DevTools:

1. פתח את ה-JS בדפדפן.
2. לחץ בקליק ימני ובחר "בדוק" כדי לפתוח את DevTools.
3. לחץ על הכרטיסיה "מקורות" (Sources).
4. חפש את קטע הקוד או הדף שלך וסמן נקודת עצירה על ידי לחיצה על מספר השורה ליד הפקודה `return`.
5. רענן את הדף כדי להפעיל את נקודת העצירה.
6. בדוק בפאנל "תחום הפעולה" (Scope) כדי לראות את המשתנים המקומיים `a` ו-`b`.
7. התקדם עם הכפתור "עבור מעל קריאת הפונקציה הבאה".
8. אתר את הבאג בפקודת ה`return`.
9. תקן את הקוד:
```javascript
function buggyMultiply(a, b) {
    return a * b; // תוקן!
}

let result = buggyMultiply(5, 3);
console.log('Result:', result);
```

הפלט המתוקן:
```
Result: 15
```

## צלילה עמוקה
המושג של ניפוי באגים קיים כבר מתחילת ימי המחשוב—האגדה אומרת שהתחיל כשמצאו פרפרת במחשב בשנות ה-40! היום, דיבאגרים ל-Javascript כמו הכלים המובנים בדפדפנים (Chrome DevTools, Firefox Developer Tools) או דיבאגרים משולבים ב-IDE (Visual Studio Code, WebStorm) מציעים מבחר עצום של תכונות.

אלטרנטיבות לדבאגרים המובנים כוללות כלים של צד שלישי כמו WebStorm או שימוש ב-`console.log` הטוב והישן לפלט מצבי משתנים. אבל אלו לא מציעים את האינטראקציה בזמן אמת והבדיקה המפורטת הניתנת על ידי דיבאגרים.

בנוגע לפרטי היישום, רוב הדיבאגרים פועלים באופן דומה: הם מאפשרים לך להגדיר נקודות עצירה שמשהים את הביצוע, להתקדם בקוד צעד אחר צעד, לבדוק את מצבי המשתנים הנוכחיים, לעקוב אחר ביטויים, ואף לשנות ערכים בזמן אמת כדי לבדוק תרחישים שונים.

## ראה גם
- [Google Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools)
- [רשת המתפתחים של מוזילה - מנפה באגים בפיירפוקס](https://developer.mozilla.org/en-US/docs/Tools/Debugger)
- [Visual Studio Code - ניפוי באגים](https://code.visualstudio.com/docs/editor/debugging)
