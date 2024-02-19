---
aliases:
- /he/google-apps-script/logging/
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:59:45.040821-07:00
description: "Logging (\u05EA\u05D9\u05E2\u05D5\u05D3) \u05D1\u05EA\u05DB\u05E0\u05D5\
  \u05EA \u05DE\u05E2\u05E8\u05D1 \u05E8\u05D9\u05E9\u05D5\u05DD \u05D0\u05D9\u05E8\
  \u05D5\u05E2\u05D9\u05DD, \u05E9\u05D2\u05D9\u05D0\u05D5\u05EA \u05D0\u05D5 \u05DE\
  \u05D5\u05E4\u05E2\u05D9\u05DD \u05E9\u05D5\u05D5\u05D9 \u05DC\u05E6\u05D9\u05D5\
  \u05DF \u05D1\u05D6\u05DE\u05DF \u05E8\u05D9\u05E6\u05D4. \u05EA\u05DB\u05E0\u05D9\
  \u05EA\u05E0\u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\
  \u05D3\u05D9 \u05DC\u05D0\u05EA\u05E8 \u05D1\u05D0\u05D2\u05D9\u05DD, \u05DC\u05E0\
  \u05D8\u05E8 \u05D1\u05D9\u05E6\u05D5\u05E2\u05D9\u05DD, \u05D5\u05DC\u05E9\u05DE\
  \u05D5\u05E8 \u05E8\u05D9\u05E9\u05D5\u05DD \u05E9\u05DC \u05E0\u05EA\u05D5\u05E0\
  \u05D9\u05DD\u2026"
lastmod: 2024-02-18 23:08:52.397305
model: gpt-4-0125-preview
summary: "Logging (\u05EA\u05D9\u05E2\u05D5\u05D3) \u05D1\u05EA\u05DB\u05E0\u05D5\u05EA\
  \ \u05DE\u05E2\u05E8\u05D1 \u05E8\u05D9\u05E9\u05D5\u05DD \u05D0\u05D9\u05E8\u05D5\
  \u05E2\u05D9\u05DD, \u05E9\u05D2\u05D9\u05D0\u05D5\u05EA \u05D0\u05D5 \u05DE\u05D5\
  \u05E4\u05E2\u05D9\u05DD \u05E9\u05D5\u05D5\u05D9 \u05DC\u05E6\u05D9\u05D5\u05DF\
  \ \u05D1\u05D6\u05DE\u05DF \u05E8\u05D9\u05E6\u05D4. \u05EA\u05DB\u05E0\u05D9\u05EA\
  \u05E0\u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\
  \u05D9 \u05DC\u05D0\u05EA\u05E8 \u05D1\u05D0\u05D2\u05D9\u05DD, \u05DC\u05E0\u05D8\
  \u05E8 \u05D1\u05D9\u05E6\u05D5\u05E2\u05D9\u05DD, \u05D5\u05DC\u05E9\u05DE\u05D5\
  \u05E8 \u05E8\u05D9\u05E9\u05D5\u05DD \u05E9\u05DC \u05E0\u05EA\u05D5\u05E0\u05D9\
  \u05DD\u2026"
title: "\u05E8\u05D9\u05E9\u05D5\u05DD"
---

{{< edit_this_page >}}

## מה ולמה?

Logging (תיעוד) בתכנות מערב רישום אירועים, שגיאות או מופעים שווי לציון בזמן ריצה. תכניתנים עושים זאת כדי לאתר באגים, לנטר ביצועים, ולשמור רישום של נתונים פעילותיים, דבר הקריטי לתחזוקה ולהבנת התנהגות התוכנה בזמן פרודקשן.

## איך לעשות:

ב-Google Apps Script, ניתן לבצע logging באמצעות שיטות שונות, כגון המחלקה `Logger` ו-`console.log()`. המחלקה Logger היא הדרך המסורתית, מתאימה לדיבאגינג פשוט ולמטרות פיתוח. עם העדכונים האחרונים, `console.log()` מציע גמישות רבה יותר ואינטגרציה עם Stackdriver Logging, מה שמספק פתרון חזק יותר לניטור ה-Apps Scripts שלך ב-Google Cloud Platform.

**שימוש ב-Logger:**

```javascript
function logSample() {
  Logger.log('זהו הודעת לוג פשוטה');
  
  var value = 5;
  Logger.log('הערך הוא: %s', value); // עיצוב מחרוזת
}

// לצפייה בלוג:
// 1. הפעל את הפונקציה logSample.
// 2. תצוגה -> יומנים
```

**דוגמא לפלט Logger:**

```
[22-04-20 10:00:00:000 PDT] זהו הודעת לוג פשוטה
[22-04-20 10:00:00:001 PDT] הערך הוא: 5
```

**שימוש ב-console.log():**

```javascript
function consoleLogSample() {
  console.log('הודעה זו מועברת ל-Stackdriver Logging');
  const obj = {name: 'Jane', role: 'Developer'};
  console.info('רישום אובייקט:', obj);
}

// הלוגים יכולים להיראות בקונסול של Google Cloud Platform (GCP) תחת Stackdriver Logging
```

**דוגמא לפלט console.log():**

```
הודעה זו מועברת ל-Stackdriver Logging
רישום אובייקט: {name: "Jane", role: "Developer"}
```

על ידי המעבר ל-`console.log()` עבור יישומים מורכבים יותר, מפתחים יכולים לנתח ולנטר לוגים באופן יעיל באמצעות המסננים והכלים החזקים המסופקים על ידי GCP, מה שלא מתאפשר בקלות עם המחלקה Logger המסורתית.

## חקירה עמוקה:

ה-Logging ב-Google Apps Script התפתח באופן משמעותי. בתחילה, המחלקה `Logger` הייתה השיטה העיקרית לתכניתנים לדיבאג את הסקריפטים שלהם. זה פשוט ומספיק לסקריפטים בסיסיים, אך חסרות לו היכולות הנדרשות ליישומי ענן מודרניים, כגון חיפוש לוגים או ניתוח מגמות לוג במהלך הזמן.

הצגת `console.log()` חתרה תחת הפער הזה על ידי אינטגרציה של תיעוד ב-Google Apps Script עם Stackdriver Logging של Google Cloud (כעת נקרא Operations Suite), מספקת פלטפורמה מרכזית לתיעוד, ניטור ודיבאג של יישומים. זה לא רק התיר תיעוד בקנה מידה, אלא גם פתח בפני מאפייני ניהול לוגים מתקדמים כמו מדדים מבוססי לוג, ניתוח לוגים בזמן אמת, ואינטגרציה עם שירותים נוספים של Google Cloud.

בזמן ש-`Logger` עדיין משרת מטרה לדיבאגינג מהיר ותיעוד בסקריפטים קטנים יותר, ההתפתחות לעבר שימוש ב-`console.log()` משקפת שינוי רחב יותר בפיתוח יישומים ענניים המותאמים לקנה מידה. זה מדגיש את מחויבותה של Google לספק למפתחים כלים התואמים למורכבות ולקנה המידה של יישומים היום. עם זאת, חדשים לתחום צריכים להיות מודעים לעקומת למידה מעט יותר תלולה ולצורך להתמצא במושגים של Google Cloud Platform. למרות זאת, המעבר מועיל למפתחים המעוניינים לנצל במלואם את היכולות הענניות. התאמה זו לשירותי הענן היא חלק ממגמה רחבה יותר בפיתוח התוכנה, המדגישה את חשיבות מנגנוני תיעוד מתקדמים וקליטים בעידן החישוב הענני.
