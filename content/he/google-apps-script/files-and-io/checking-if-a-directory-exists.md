---
aliases:
- /he/google-apps-script/checking-if-a-directory-exists/
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:50:07.572417-07:00
description: "\u05D1\u05D3\u05D9\u05E7\u05D4 \u05D0\u05DD \u05E1\u05E4\u05E8\u05D9\
  \u05D4 \u05E7\u05D9\u05D9\u05DE\u05EA \u05D1- Google Apps Script \u05DB\u05D5\u05DC\
  \u05DC\u05EA \u05D0\u05D9\u05DE\u05D5\u05EA \u05E9\u05DC \u05E7\u05D9\u05D5\u05DD\
  \ \u05EA\u05D9\u05E7\u05D9\u05D4 \u05D1\u05EA\u05D5\u05DA Google Drive. \u05DE\u05EA\
  \u05DB\u05E0\u05EA\u05D9\u05DD \u05DC\u05E2\u05D9\u05EA\u05D9\u05DD \u05E7\u05E8\
  \u05D5\u05D1\u05D5\u05EA \u05DE\u05D1\u05E6\u05E2\u05D9\u05DD \u05D0\u05EA \u05D4\
  \u05D1\u05D3\u05D9\u05E7\u05D4 \u05D4\u05D6\u05D5 \u05DB\u05D3\u05D9 \u05DC\u05D4\
  \u05D9\u05DE\u05E0\u05E2 \u05DE\u05E9\u05D2\u05D9\u05D0\u05D5\u05EA \u05D0\u05D5\
  \u2026"
lastmod: 2024-02-18 23:08:52.406528
model: gpt-4-0125-preview
summary: "\u05D1\u05D3\u05D9\u05E7\u05D4 \u05D0\u05DD \u05E1\u05E4\u05E8\u05D9\u05D4\
  \ \u05E7\u05D9\u05D9\u05DE\u05EA \u05D1- Google Apps Script \u05DB\u05D5\u05DC\u05DC\
  \u05EA \u05D0\u05D9\u05DE\u05D5\u05EA \u05E9\u05DC \u05E7\u05D9\u05D5\u05DD \u05EA\
  \u05D9\u05E7\u05D9\u05D4 \u05D1\u05EA\u05D5\u05DA Google Drive. \u05DE\u05EA\u05DB\
  \u05E0\u05EA\u05D9\u05DD \u05DC\u05E2\u05D9\u05EA\u05D9\u05DD \u05E7\u05E8\u05D5\
  \u05D1\u05D5\u05EA \u05DE\u05D1\u05E6\u05E2\u05D9\u05DD \u05D0\u05EA \u05D4\u05D1\
  \u05D3\u05D9\u05E7\u05D4 \u05D4\u05D6\u05D5 \u05DB\u05D3\u05D9 \u05DC\u05D4\u05D9\
  \u05DE\u05E0\u05E2 \u05DE\u05E9\u05D2\u05D9\u05D0\u05D5\u05EA \u05D0\u05D5\u2026"
title: "\u05D1\u05D3\u05D9\u05E7\u05D4 \u05D0\u05DD \u05E1\u05E4\u05E8\u05D9\u05D9\
  \u05D4 \u05E7\u05D9\u05D9\u05DE\u05EA"
---

{{< edit_this_page >}}

## מה ולמה?

בדיקה אם ספריה קיימת ב- Google Apps Script כוללת אימות של קיום תיקיה בתוך Google Drive. מתכנתים לעיתים קרובות מבצעים את הבדיקה הזו כדי להימנע משגיאות או יצירת תיקיות שכפולות בזמן ניהול קבצים ותיקיות באופן תכנותי.

## איך לעשות:

Google Apps Script אינה מציעה שיטה ישירה של "קיים" לתיקיות. במקום זאת, אנו משתמשים ביכולת החיפוש של Google Drive כדי לבדוק אם קיימת תיקיה עם שם מסוים. הנה דוגמא צעד אחר צעד:

```javascript
// פונקציה לבדוק אם ספריה קיימת
function checkIfDirectoryExists(directoryName) {
  // אחזר את אוסף התיקיות התואמות את השם שצוין
  var folders = DriveApp.getFoldersByName(directoryName);
  
  // בדוק אם קיימת לפחות תיקיה אחת עם השם שצוין
  if (folders.hasNext()) {
    Logger.log('הספריה קיימת.');
    return true;
  } else {
    Logger.log('הספריה לא קיימת.');
    return false;
  }
}

// דוגמא לשימוש
var directoryName = 'My Sample Folder';
checkIfDirectoryExists(directoryName);
```

פלט לדוגמא:
```
הספריה קיימת.
```
או 
```
הספריה לא קיימת.
```

הסקריפט הזה מנצל את השיטה `getFoldersByName` אשר מאחזרת את כל התיקיות ב-Drive של המשתמש התואמות לשם שצוין. מכיוון שהשמות אינם ייחודיים ב-Drive, שיטה זו מחזירה `FolderIterator`. נוכחות של פריט הבא (`hasNext()`) באיטרטור זה מורה על כך שהספריה קיימת.

## ניתוח עמוק

בהיסטוריה, ניהול קבצים בסביבות רשת וענן התפתח משמעותית. Google Apps Script, המספקת API מקיף ל-Google Drive, מאפשרת פעולות ניהול קבצים ותיקיות מתוחכמות, כולל מנגנוני חיפוש ובדיקה כפי שהוצגו. עם זאת, היבט בולט הוא היעדר שיטת בדיקת קיום ישירה, ככל הנראה בשל האפשרות של Google Drive לאפשר מספר תיקיות בעלות אותו שם, מה שנוגד את רבות ממערכות הקבצים המחייבות שמות ייחודיים בתוך אותה תיקיה.

בהקשר זה, שימוש בשיטת `getFoldersByName` היא פתרון עקיף אך יעיל, אך עשוי להכניס חוסר יעילות בתרחיש בו קיימות מספרים גדולים של תיקיות עם שמות כפולים. גישה חלופית עשויה להיות שמירה על אינדקס או קונבנציה של שמות ספציפיים לאפליקציה, על מנת להבטיח בדיקות מהירות יותר, במיוחד כאשר הביצועים הופכים לדאגת מרכזית.

למרות שהגישה של Google Apps Script עשויה להיראות בתחילה כפחות ישירה לעומת בדיקות קיום קבצים בשפות תכנות הממוקמות ישירות עם מערכת קבצים יחידה, היא משקפת את הצורך להתמודד עם מורכבויות האחסון הבסיסי בענן. מפתחים המנצלים את Google Apps Script לניהול Drive צריכים לשקול את העדינויות הללו, ולשאוף למיטוב בהתאם לחוזקות ולהגבלות של Google Drive.
