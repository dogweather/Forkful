---
title:                "פרסום תאריך ממחרוזת"
aliases:
- /he/typescript/parsing-a-date-from-a-string/
date:                  2024-02-03T19:16:13.749306-07:00
model:                 gpt-4-0125-preview
simple_title:         "פרסום תאריך ממחרוזת"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/typescript/parsing-a-date-from-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## מה ולמה?
לעבד תאריך ממחרוזת כולל המרת ייצוגים טקסטואליים של תאריכים ושעות לפורמט שניתן לניפוי וניתוח על ידי התוכנית. זו משימה נפוצה בתכנות כיוון שהיא מאפשרת טיפול בקלט מהמשתמש, אחסון נתונים עם חותמת זמן, ואינטראקציות עם ממשקי תכנות יישומים (APIs), וכך מובילה ליישומים יותר פונקציונליים ונוחים למשתמש.

## איך לעשות זאת:
TypeScript, שהוא תת-קבוצה של JavaScript, מסתמך על אובייקט התאריך לצורך עיבוד תאריכים ממחרוזות. עם זאת, העבודה עם תאריכים ב-JS/TS יכולה להיות מפורטת או לא מדויקת בשל החסרונות של אובייקט התאריך. להלן דוגמה בסיסית אחריה גישה באמצעות ספרייה פופולרית, `date-fns`, לפתרונות עמידים יותר.

### באמצעות אובייקט התאריך של JavaScript
```typescript
// ניתוח בסיסי באמצעות בנאי התאריך
const dateFromString = new Date("2023-04-21T15:00:00Z");
console.log(dateFromString.toString()); 
// פלט ל-GMT: "Fri Apr 21 2023 15:00:00 GMT+0000 (Coordinated Universal Time)"
```

שיטה זו עובדת עבור מחרוזות בפורמט ISO וכמה פורמטים אחרים של תאריכים, אך עשויה להניב תוצאות לא עקביות עבור פורמטים לא ברורים בין דפדפנים ואזורים שונים.

### באמצעות date-fns
הספרייה `date-fns` מספקת טיפול ישיר ועקבי בתאריכים. זו ספרייה מודולרית, מה שמאפשר לך לכלול רק את החלקים שאתה זקוק להם, מה שמקטין את גודל החבילה.

ראשית, התקן את `date-fns`: 

```sh
npm install date-fns
```

לאחר מכן, השתמש בה לעיבוד מחרוזת תאריך:

```typescript
import { parseISO, format } from 'date-fns';

// ניתוח מחרוזת ISO
const dateString = "2023-04-21T15:00:00Z";
const parsedDate = parseISO(dateString);

// עיצוב התאריך (למשל, לצורה קריאה לאנוש)
console.log(format(parsedDate, "PPPpp")); 
// פלט: "Apr 21st, 2023 at 3:00 PM" (הפלט עשוי להשתנות בהתאם לאזור)
```

`date-fns` תומך במגוון רחב של פורמטים ואזורים, מה שהופך אותו לבחירה עמידה עבור יישומים שדורשים עיבוד ועיצוב תאריכים מדויקים באזורים שונים של משתמשים.
