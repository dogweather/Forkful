---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:01:40.733953-07:00
description: "Refactoring (\u05E9\u05D9\u05E4\u05D5\u05E8 \u05E7\u05D5\u05D3) \u05D1\
  \u05DE\u05D9\u05DC\u05D5\u05DF \u05D4\u05EA\u05DB\u05E0\u05D5\u05EA \u05DE\u05EA\
  \u05D9\u05D9\u05D7\u05E1 \u05DC\u05EA\u05D4\u05DC\u05D9\u05DA \u05E9\u05DC \u05DE\
  \u05D1\u05E0\u05D4 \u05DE\u05D7\u05D3\u05E9 \u05E9\u05DC \u05E7\u05D5\u05D3 \u05DE\
  \u05D7\u05E9\u05D1 \u05E7\u05D9\u05D9\u05DD - \u05E9\u05D9\u05E0\u05D5\u05D9 \u05D4\
  \u05DE\u05D1\u05E0\u05D4 \u05DC\u05DC\u05D0 \u05E9\u05D9\u05E0\u05D5\u05D9 \u05D1\
  \u05D4\u05EA\u05E0\u05D4\u05D2\u05D5\u05EA \u05D4\u05D7\u05D9\u05E6\u05D5\u05E0\u05D9\
  \u05EA \u05E9\u05DC\u05D5 \u2013 \u05E2\u05DC \u05DE\u05E0\u05EA \u05DC\u05E9\u05E4\
  \u05E8 \u05EA\u05DB\u05D5\u05E0\u05D5\u05EA \u05DC\u05D0\u2026"
lastmod: '2024-03-13T22:44:38.579848-06:00'
model: gpt-4-0125-preview
summary: "Refactoring (\u05E9\u05D9\u05E4\u05D5\u05E8 \u05E7\u05D5\u05D3) \u05D1\u05DE\
  \u05D9\u05DC\u05D5\u05DF \u05D4\u05EA\u05DB\u05E0\u05D5\u05EA \u05DE\u05EA\u05D9\
  \u05D9\u05D7\u05E1 \u05DC\u05EA\u05D4\u05DC\u05D9\u05DA \u05E9\u05DC \u05DE\u05D1\
  \u05E0\u05D4 \u05DE\u05D7\u05D3\u05E9 \u05E9\u05DC \u05E7\u05D5\u05D3 \u05DE\u05D7\
  \u05E9\u05D1 \u05E7\u05D9\u05D9\u05DD - \u05E9\u05D9\u05E0\u05D5\u05D9 \u05D4\u05DE\
  \u05D1\u05E0\u05D4 \u05DC\u05DC\u05D0 \u05E9\u05D9\u05E0\u05D5\u05D9 \u05D1\u05D4\
  \u05EA\u05E0\u05D4\u05D2\u05D5\u05EA \u05D4\u05D7\u05D9\u05E6\u05D5\u05E0\u05D9\u05EA\
  \ \u05E9\u05DC\u05D5 \u2013 \u05E2\u05DC \u05DE\u05E0\u05EA \u05DC\u05E9\u05E4\u05E8\
  \ \u05EA\u05DB\u05D5\u05E0\u05D5\u05EA \u05DC\u05D0 \u05E4\u05D5\u05E0\u05E7\u05E6\
  \u05D9\u05D5\u05E0\u05DC\u05D9\u05D5\u05EA."
title: "\u05E9\u05D9\u05E4\u05D5\u05E8 \u05E7\u05D5\u05D3"
weight: 19
---

## איך לעשות:
ב-Google Apps Script, תרחיש נפוץ המרוויח משיפור הוא הפשטת סקריפטים מסורבלים המתקשרים עם Google Sheets או Docs. בהתחלה, סריפטים עשויים להיכתב בדרך מהירה ולא מסודרת כדי לקבל תוצאות מהר. עם הזמן, ככל שהסקריפט מתרחב, הוא הופך להיות כבד. בואו נעבור על דוגמה של שיפור לקריאות ויעילות טובה יותר.

**סקריפט מקורי:**

```javascript
function logSheetNames() {
  var sheets = SpreadsheetApp.getActiveSpreadsheet().getSheets();
  for (var i = 0; i < sheets.length; i++) {
    Logger.log(sheets[i].getName());
  }
}
```

פונקציה זו מתעדת את שם כל גיליון ב-Google Spreadsheet. למרות שהיא פועלת טוב, היא משתמשת בתרגולי JavaScript ישנים וחסרה בהירות.

**סקריפט שופר:**

```javascript
function logSheetNames() {
  const sheets = SpreadsheetApp.getActiveSpreadsheet().getSheets();
  sheets.forEach(sheet => Logger.log(sheet.getName()));
}
```

בגרסה השופרת, החלפנו לשימוש ב-`const` עבור משתנים שלא משתנים, הופך את כוונתנו לברורה יותר. כמו כן, השתמשנו במתודת `forEach`, גישה מודרנית ותמציתית יותר לעיבוד של מערכים, תוך שיפור הקריאות.

**פלט לדוגמה (עבור שני הסקריפטים):**

הפלט ב-Logger יראה משהו כזה, בהנחה שהמסמך Google Sheets שלך כולל שני גליונות בשמות "Expenses" ו-"Revenue":

```
[20-04-2023 10:00:00: INFO] Expenses
[20-04-2023 10:00:01: INFO] Revenue
```

הסקריפט השופר השיג את אותה התוצאה אך הוא נקי וקל יותר להבנה ממבט ראשון.

## צלילה עמוקה
שיפור ב-Google Apps Script מוריש חלק מעקרונותיו מהתרגול ההנדסי התוכנה הרחב יותר. הוא התקבל ונבנה כמושג באופן מובנה יותר בשנות ה-90 המאוחרות, בעיקר בזכות הספר החשוב של מרטין פאולר "Refactoring: Improving the Design of Existing Code" (1999), שסיפק מדריך מקיף לטכניקות שיפור שונות. למרות שפרטי השיפור יכולים להשתנות בהתאם לשפות תכנות בגלל ההבדלים התחביריים והפונקציונליים שלהן, המטרה המרכזית נשארת זהה: לשפר את הקוד ללא שינוי בהתנהגותו החיצונית.

בהקשר של Google Apps Script, אספקט חשוב לשקול במהלך השיפור הוא מכסות והגבלות השירות המוטלות על ידי Google. קוד ששופר ביעילות לא רק נקרא טוב יותר אלא גם פועל מהר יותר ובאמינות גבוהה יותר בתוך המגבלות הללו. לדוגמה, פעולות אצווה (`Range.setValues()` במקום להגדיר ערכים תא אחר תא) יכולות להפחית באופן משמעותי את זמן הביצוע וצריכת המכסה.

חשוב לציין, עם זאת, כי לפרויקטים מורכבים מסוימים, Google Apps Script עשוי להיקלע לקוצר בגלל המגבלות הללו. במקרים כאלה, התבוננות באלטרנטיבות כמו Google Cloud Functions או קרוב משפחה חדש יותר של Apps Script, AppSheet, עשויה להציע גמישות ופונקציונליות טובה יותר.

בסופו של דבר, בעוד ששיפור הוא מיומנות קריטית בתחזוקה ושיפור פרויקטים של Google Apps Script, הבנת הגבלות הסביבה ושקילת פתרונות חלופיים היא חשובה לא פחות לספק קוד יעיל, אמין, ושמיר.
