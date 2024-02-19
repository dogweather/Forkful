---
aliases:
- /he/javascript/creating-a-temporary-file/
date: 2024-01-20 17:41:00.623223-07:00
description: "\u05D9\u05E6\u05D9\u05E8\u05EA \u05E7\u05D5\u05D1\u05E5 \u05D6\u05DE\
  \u05E0\u05D9 \u05DE\u05D0\u05E4\u05E9\u05E8\u05EA \u05E9\u05DE\u05D9\u05E8\u05EA\
  \ \u05DE\u05D9\u05D3\u05E2 \u05D1\u05D0\u05D5\u05E4\u05DF \u05E2\u05E7\u05D9\u05E3\
  \ \u05DC\u05E4\u05E0\u05D9 \u05E4\u05E8\u05E1\u05D5\u05DD \u05D0\u05D5 \u05D0\u05D7\
  \u05E1\u05D5\u05DF \u05E1\u05D5\u05E4\u05D9. \u05EA\u05DB\u05E0\u05D9\u05EA\u05E0\
  \u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9\
  \ \u05DC\u05E2\u05D1\u05D3 \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD \u05D1\u05D0\u05D5\
  \u05E4\u05DF \u05D6\u05DE\u05E0\u05D9, \u05DC\u05DE\u05D6\u05E2\u05D5\u05E8 \u05D0\
  \u05EA \u05D4\u05E9\u05D9\u05DE\u05D5\u05E9 \u05D1\u05D6\u05D9\u05DB\u05E8\u05D5\
  \u05DF, \u05D5\u05DC\u05D8\u05E4\u05DC\u2026"
lastmod: 2024-02-18 23:08:53.268777
model: gpt-4-1106-preview
summary: "\u05D9\u05E6\u05D9\u05E8\u05EA \u05E7\u05D5\u05D1\u05E5 \u05D6\u05DE\u05E0\
  \u05D9 \u05DE\u05D0\u05E4\u05E9\u05E8\u05EA \u05E9\u05DE\u05D9\u05E8\u05EA \u05DE\
  \u05D9\u05D3\u05E2 \u05D1\u05D0\u05D5\u05E4\u05DF \u05E2\u05E7\u05D9\u05E3 \u05DC\
  \u05E4\u05E0\u05D9 \u05E4\u05E8\u05E1\u05D5\u05DD \u05D0\u05D5 \u05D0\u05D7\u05E1\
  \u05D5\u05DF \u05E1\u05D5\u05E4\u05D9. \u05EA\u05DB\u05E0\u05D9\u05EA\u05E0\u05D9\
  \u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9 \u05DC\
  \u05E2\u05D1\u05D3 \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD \u05D1\u05D0\u05D5\u05E4\
  \u05DF \u05D6\u05DE\u05E0\u05D9, \u05DC\u05DE\u05D6\u05E2\u05D5\u05E8 \u05D0\u05EA\
  \ \u05D4\u05E9\u05D9\u05DE\u05D5\u05E9 \u05D1\u05D6\u05D9\u05DB\u05E8\u05D5\u05DF\
  , \u05D5\u05DC\u05D8\u05E4\u05DC\u2026"
title: "\u05D9\u05E6\u05D9\u05E8\u05EA \u05E7\u05D5\u05D1\u05E5 \u05D6\u05DE\u05E0\
  \u05D9"
---

{{< edit_this_page >}}

## מה ולמה?
יצירת קובץ זמני מאפשרת שמירת מידע באופן עקיף לפני פרסום או אחסון סופי. תכניתנים עושים זאת כדי לעבד נתונים באופן זמני, למזעור את השימוש בזיכרון, ולטפל בניהול תהליכים שקורים במקביל.

## איך לעשות:
ב-JavaScript על מנת ליצור קובץ זמני ניתן להשתמש בחבילות כמו `fs` ו-`tmp`. דוגמה:

```javascript
const fs = require('fs');
const tmp = require('tmp');

// יצירת קובץ זמני
tmp.file(function _tempFileCreated(err, path, fd, cleanupCallback) {
  if (err) throw err;

  console.log('קובץ זמני נוצר ב:', path);
  // כתיבה לקובץ
  fs.writeFileSync(path, 'שלום, זה טקסט לדוגמה!');
  
  // קריאה מהקובץ
  const content = fs.readFileSync(path, 'utf8');
  console.log(content);

  // ניקוי ומחיקת הקובץ
  cleanupCallback();
});
```

דוגמת פלט:
```
קובץ זמני נוצר ב: /tmp/tmp-1234abcd
שלום, זה טקסט לדוגמה!
```

## עומק ידע:
בעבר, יצירת קובצים זמניים התבצעה בצורה ידנית ולא ממומשת באמצעות ספריות. השתמשנו בשמות קובץ ייחודיים כדי למנוע התנגשויות. כיום, ספריות כמו `tmp` מספקות מנגנון מובנה לניהול קבצים זמניים בצורה מאובטחת, עם אפשרות למחיקה אוטומטית שלהם. חלופות לשימוש ב`tmp` יכולות לכלול שימוש ספריות כמו `mktemp` במערכות Unix או כתיבת התקנה ידנית.

## ראה גם:
- [מסמך Node.js על המודול fs](https://nodejs.org/api/fs.html)
- [מסמך הספריה `tmp`](https://www.npmjs.com/package/tmp)
