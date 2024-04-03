---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:05:02.979567-07:00
description: "\u05DE\u05E2\u05E8\u05DB\u05D9\u05DD \u05D0\u05E1\u05D5\u05E6\u05D9\u05D0\
  \u05D8\u05D9\u05D1\u05D9\u05D9\u05DD, \u05D4\u05D9\u05D3\u05D5\u05E2\u05D9\u05DD\
  \ \u05DB\u05D0\u05D5\u05D1\u05D9\u05D9\u05E7\u05D8\u05D9\u05DD \u05D1-Google Apps\
  \ Script (\u05D2\u05E8\u05E1\u05EA \u05D2'\u05D0\u05D5\u05D5\u05D4\u05E1\u05E7\u05E8\
  \u05D9\u05E4\u05D8), \u05DE\u05D0\u05E4\u05E9\u05E8\u05D9\u05DD \u05DC\u05DE\u05EA\
  \u05DB\u05E0\u05EA\u05D9\u05DD \u05DC\u05D9\u05E6\u05D5\u05E8 \u05D0\u05D5\u05E1\
  \u05E4\u05D9\u05DD \u05E9\u05DC \u05D6\u05D5\u05D2\u05D5\u05EA \u05DE\u05E4\u05EA\
  \u05D7-\u05E2\u05E8\u05DA. \u05E4\u05D5\u05E0\u05E7\u05E6\u05D9\u05D5\u05E0\u05DC\
  \u05D9\u05D5\u05EA \u05D6\u05D5 \u05D4\u05D9\u05D0\u2026"
lastmod: '2024-03-13T22:44:38.552664-06:00'
model: gpt-4-0125-preview
summary: "\u05DE\u05E2\u05E8\u05DB\u05D9\u05DD \u05D0\u05E1\u05D5\u05E6\u05D9\u05D0\
  \u05D8\u05D9\u05D1\u05D9\u05D9\u05DD, \u05D4\u05D9\u05D3\u05D5\u05E2\u05D9\u05DD\
  \ \u05DB\u05D0\u05D5\u05D1\u05D9\u05D9\u05E7\u05D8\u05D9\u05DD \u05D1-Google Apps\
  \ Script (\u05D2\u05E8\u05E1\u05EA \u05D2'\u05D0\u05D5\u05D5\u05D4\u05E1\u05E7\u05E8\
  \u05D9\u05E4\u05D8), \u05DE\u05D0\u05E4\u05E9\u05E8\u05D9\u05DD \u05DC\u05DE\u05EA\
  \u05DB\u05E0\u05EA\u05D9\u05DD \u05DC\u05D9\u05E6\u05D5\u05E8 \u05D0\u05D5\u05E1\
  \u05E4\u05D9\u05DD \u05E9\u05DC \u05D6\u05D5\u05D2\u05D5\u05EA \u05DE\u05E4\u05EA\
  \u05D7-\u05E2\u05E8\u05DA."
title: "\u05E9\u05D9\u05DE\u05D5\u05E9 \u05D1\u05DE\u05E2\u05E8\u05DB\u05D9\u05DD\
  \ \u05D0\u05E1\u05D5\u05E6\u05D9\u05D0\u05D8\u05D9\u05D1\u05D9\u05D9\u05DD"
weight: 15
---

## איך:
ב-Google Apps Script, אתה יוצר ומניפל מערכים אסוציאטיביים (אובייקטים) באמצעות סוגריים מסולסלים `{}`, ומגדיר בתוכם זוגות מפתח-ערך. המפתחות הם מזהים ייחודיים, והערכים יכולים להיות החל ממחרוזות ומספרים ועד לאובייקטים או פונקציות יותר מורכבים. הנה דוגמה בסיסית:

```javascript
function createAssociativeArray() {
  var user = {
    name: "John Doe",
    age: 30,
    email: "johndoe@example.com"
  };

  // גישה לערכים
  Logger.log(user.name); // מוציא: John Doe
  Logger.log(user["email"]); // מוציא: johndoe@example.com

  // הוספת זוגות מפתח-ערך חדשים
  user.title = "Software Developer";
  user["country"] = "USA";

  Logger.log(user.title); // מוציא: Software Developer

  // איטרציה על זוגות מפתח-ערך
  for (var key in user) {
    Logger.log(key + ': ' + user[key]);
  }
}
```

דוגמה לפלט עבור החלק של האיטרציה עשויה להיראות כך:
```
name: John Doe
age: 30
email: johndoe@example.com
title: Software Developer
country: USA
```

שימו לב כיצד ניתן להשתמש בסימון נקודה ובסימון סוגריים לגישה והגדרה של תכונות. סימון סוגריים שימושי במיוחד כאשר עובדים עם מפתחות הנקבעים באופן דינמי או כוללים תווים שאינם מותרים במזהים.

## צלילה עמוקה
מערכים אסוציאטיביים בצורת אובייקטים היוו אבן פינה בג'אווהסקריפט, ובהרחבה ב-Google Apps Script, המשקפת את מנגנון הירושה מבוסס הפרוטוטיפ שלה. בניגוד לשפות עם מערכים אסוציאטיביים או מילונים טרדיציונליים (למשל, dict של פייתון), אובייקטים ב-Google Apps Script מספקים אמצעי גמיש וחזק למבנה נתונים, נהנים מהטבע הדינמי של ג'אווהסקריפט.

עם זאת, חשוב לציין שהתקנת ECMAScript 2015 הציגה את האובייקטים `Map` ו-`Set`, המציעים טיפול ישיר יותר באוספים אסוציאטיביים עם יתרונות מסוימים על פני אובייקטים, כמו שמירה על סדר ההכנסה וביצועים טובים יותר עבור מערכי נתונים גדולים. למרות ש-Google Apps Script תומכת גם באלה, הבחירה בין שימוש באובייקטים לבין מבנים חדשים יותר של `Map`/`Set` תלויה בצרכים ספציפיים ובשיקולי ביצועים. עבור רוב משימות המערך האסוציאטיבי, היישומים המבוססים על אובייקטים מספקים גישה מוכרת ורבת גמישות, אך מומלץ לבחון אלטרנטיבות חדשות יותר ככל שמורכבות הסקריפט שלך גדלה.
