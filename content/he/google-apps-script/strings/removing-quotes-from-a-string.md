---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:01:28.409371-07:00
description: "\u05D4\u05E1\u05E8\u05EA \u05E6\u05D9\u05D8\u05D5\u05D8\u05D9\u05DD\
  \ \u05DE\u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05D1-Google Apps Script \u05E2\u05D5\
  \u05E1\u05E7\u05EA \u05D1\u05D4\u05E1\u05E8\u05EA \u05E1\u05D9\u05DE\u05E0\u05D9\
  \ \u05E6\u05D9\u05D8\u05D5\u05D8 \u05DE\u05D9\u05D5\u05EA\u05E8\u05D9\u05DD \u05E9\
  \u05E2\u05E9\u05D5\u05D9\u05D9\u05DD \u05DC\u05D4\u05E7\u05D9\u05E3 \u05D0\u05EA\
  \ \u05E0\u05EA\u05D5\u05E0\u05D9 \u05D4\u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05E9\
  \u05DC\u05DA, \u05E9\u05D1\u05D3\u05E8\u05DA \u05DB\u05DC\u05DC \u05E0\u05D5\u05D1\
  \u05E2\u05D9\u05DD \u05DE\u05D0\u05D5\u05D1\u05D9\u05D9\u05E7\u05D8\u05D9\u05DD\
  \ \u05E9\u05DC JSON \u05E9\u05E0\u05E4\u05E8\u05E1\u05D5,\u2026"
lastmod: '2024-03-13T22:44:38.544155-06:00'
model: gpt-4-0125-preview
summary: "\u05D4\u05E1\u05E8\u05EA \u05E6\u05D9\u05D8\u05D5\u05D8\u05D9\u05DD \u05DE\
  \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05D1-Google Apps Script \u05E2\u05D5\u05E1\
  \u05E7\u05EA \u05D1\u05D4\u05E1\u05E8\u05EA \u05E1\u05D9\u05DE\u05E0\u05D9 \u05E6\
  \u05D9\u05D8\u05D5\u05D8 \u05DE\u05D9\u05D5\u05EA\u05E8\u05D9\u05DD \u05E9\u05E2\
  \u05E9\u05D5\u05D9\u05D9\u05DD \u05DC\u05D4\u05E7\u05D9\u05E3 \u05D0\u05EA \u05E0\
  \u05EA\u05D5\u05E0\u05D9 \u05D4\u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05E9\u05DC\
  \u05DA, \u05E9\u05D1\u05D3\u05E8\u05DA \u05DB\u05DC\u05DC \u05E0\u05D5\u05D1\u05E2\
  \u05D9\u05DD \u05DE\u05D0\u05D5\u05D1\u05D9\u05D9\u05E7\u05D8\u05D9\u05DD \u05E9\
  \u05DC JSON \u05E9\u05E0\u05E4\u05E8\u05E1\u05D5, \u05E7\u05DC\u05D8 \u05DE\u05E9\
  \u05EA\u05DE\u05E9, \u05D0\u05D5 \u05D7\u05D9\u05DC\u05D5\u05E5 \u05E0\u05EA\u05D5\
  \u05E0\u05D9\u05DD."
title: "\u05D4\u05E1\u05E8\u05EA \u05DE\u05E8\u05DB\u05D0\u05D5\u05EA \u05DE\u05DE\
  \u05D7\u05E8\u05D5\u05D6\u05EA"
weight: 9
---

## איך לעשות:
Google Apps Script לא נופל מרחוק מהתרגלות הסטנדרטית של JavaScript לגבי טיפול במחרוזות והתעסקות בהן. לשם הסרת ציטוטים ממחרוזת, אפשר להיעזר בשיטת ה-`replace()`, המאפשרת החלפת חלקים במחרוזת באמצעות ביטויים רגולריים. הנה דוגמה מהירה:

```javascript
function removeQuotes() {
  var stringWithQuotes = '"This is a string surrounded by quotes"';
  // השתמשו בביטוי רגולרי כדי להחליף ציטוטים בכלום
  var stringWithoutQuotes = stringWithQuotes.replace(/^"|"$/g, '');
  Logger.log(stringWithoutQuotes); // יומן: This is a string surrounded by quotes
}
```

ה-`^"` מכוון לציטוט שבהתחלת המחרוזת, ו-`"$` מכוון לציטוט בסוף המחרוזת. המסנן `g` מבטיח שהביטוי יחול על כל המחרוזת באופן גלובלי. שיטה זו מהירה, פשוטה, ומכוונת באופן ספציפי רק לציטוטים החיצוניים ביותר של המחרוזת.

הנה תסריט נוסף הכולל ציטוטים בודדים:

```javascript
function removeSingleQuotes() {
  var stringWithSingleQuotes = "'Here's a string with single quotes'";
  var stringWithoutSingleQuotes = stringWithSingleQuotes.replace(/^'|'$/g, '');
  Logger.log(stringWithoutSingleQuotes); // יומן: Here's a string with single quotes
}
```

שיטות אלו מתאימות היטב למשימות פשוטות של הסרת ציטוטים אך עשויות לזקוק לשיפור עבור מחרוזות מורכבות יותר או סוגים שונים של תווים מקיפים.

## טבילה עמוקה
הטכניקה של הסרת ציטוטים ממחרוזות באמצעות ביטויים רגולריים קיימת מראשית ימי התכנות, והיא מתאימה לעצמה ככל שהשפות מתפתחות. בשפת Google Apps Script, הניצול של יכולות ניהול המחרוזות החזקות של JavaScript, כולל ביטויים רגולריים, מספק למפתחים ערכת כלים עוצמתית. עם זאת, חשוב לשים לב למגבלות ולמלכודות הפוטנציאליות: בעיקר, שגישה זו מניחה שהציטוטים נמצאים רק בהתחלה ובסוף המחרוזת. ציטוטים מוטמעים או ציטוטים שנועדו כחלק מנתוני המחרוזת עלולים להיסרק בטעות אם לא יתוקנו בהתאמה.

עבור תסריטים מורכבים יותר, כמו ציטוטים מקוננים או הסרת ציטוטים באופן בררני רק כאשר הם מקיפים את המחרוזת, יתכן שיהיה צורך בגישה עדינה יותר או במפענח. ספריות או פונקציות מובנות בשפות אחרות, כמו השיטה `strip()` ב-Python, מציעות את הפונקציונליות הללו מחוץ לקופסה, מדגימות את ההבדל בין פשטותו של Google Apps Script לבין פונקציונליות המיוחדת והעשירה של סביבות תכנות אחרות.

בפועל, בעוד שהשיטה `replace()` בשילוב עם ביטויים רגולריים מציעה פתרון מהיר ונגיש, על מפתחים לשקול את הקשר של הנתונים שלהם ואת הספציפיות של הצרכים שלהם. ייתכן שיהיה צורך בשיטות חלופיות או בבדיקות נוספות כדי לנקות ולעבד מחרוזות באופן עמוק, ולשמר את האמינות והאמינות של מניפולציות הנתונים ב-Google Apps Script. זה מדגיש את חשיבות ההבנה של הכלים שעומדים לרשותך ואת הנואנסים של הנתונים שעמם אתה עובד, ומבטיח שהפונקציונליות תתאים בצורה הדוקה למיוחדות של השימוש הספציפי שלך.
