---
title:                "שימוש בדיבאגר"
aliases:
- /he/typescript/using-a-debugger/
date:                  2024-01-26T04:12:00.757314-07:00
model:                 gpt-4-0125-preview
simple_title:         "שימוש בדיבאגר"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/typescript/using-a-debugger.md"
---

{{< edit_this_page >}}

## מה ולמה?
מנפה (Debugger) הוא כלי שמאפשר לך לבחון ולשנות את פנימיות הקוד שלך בזמן שהוא רץ. מתכנתים משתמשים בו כדי ללחוץ באגים על ידי צעד בצעד דרך הקוד שלהם, בדיקת משתנים, והבנת זרימת התוכנית שלהם.

## איך ל:

כדי להתחיל לעבוד עם מנפה בTypeScript, כל מה שאתה צריך זה IDE נתמך (כמו Visual Studio Code) וקובץ תצורה `launch.json`. הנה דוגמה מהירה ליישום Node.js:

```TypeScript
// app.ts
function greet(name: string) {
    console.log(`שלום, ${name}!`);
}

const userName = 'Ada';
greet(userName);
```

כדי לנפות את זה, צור קובץ `launch.json` תחת תיקיית ה`.vscode`:

```JSON
{
    "version": "0.2.0",
    "configurations": [
        {
            "type": "node",
            "request": "launch",
            "name": "הפעלת תוכנית",
            "skipFiles": ["<node_internals>/**"],
            "program": "${workspaceFolder}/app.ts",
            "preLaunchTask": "tsc: build - tsconfig.json",
            "outFiles": ["${workspaceFolder}/build/**/*.js"]
        }
    ]
}
```

לאחר מכן, הגדר נקודת עצירה בפונקציה `greet` שלך על ידי לחיצה על צד שמאל של מספר השורה ב-IDE שלך. לחץ על F5 כדי להתחיל בניפוי, ותצפה כיצד האפליקציה שלך עוצרת בנקודת העצירה. כעת אתה יכול להרחיף מעל משתנים, לצפות בביטויים, ולצעוד דרך הקוד שלך בקלות.

## צלילה עמוקה

בימים שלפני שסביבות הפיתוח המשולבות (IDEs) הפכו חלקות, ניפוי היה לעיתים קרובות נעשה באמצעות הודעות הדפסה (ידוע גם כ`console.log` debugging). זה עבד, במידת מה, אך היה כמו לנסות למצוא מחט בערמת קש מחובש.

מנפים מודרניים הם כמו סכין שוויצרית לפתרון בעיות. עם התפתחות TypeScript ו-Node.js, ישנם מנפים שונים זמינים, החל ממפקח הפנימי של Node.js ועד לכלים פיתוחיים של הדפדפן לניפוי בצד הלקוח.

מפקח ה-Node.js פועל על ידי התחברות ליישום הרץ שלך; הוא מתקשר דרך פרוטוקול Chrome DevTools, הופך את הדפדפן Chrome שלך לקונסולת ניפוי עוצמתית. האינטגרציה הזו מאפשרת מושב ניפוי מפורט ואינטראקטיבי מבחינה חזותית, לעומת הנהלים מסורתיים של ניפוי בשורת הפקודה.

## ראה גם

לקריאה נוספת וכמה טיפים מקצועיים, בדוק את:

- [ניפוי TypeScript ב-Visual Studio Code](https://code.visualstudio.com/docs/typescript/typescript-debugging)
- [מדריך ניפוי Node.js](https://nodejs.org/en/docs/guides/debugging-getting-started/)
- [תיעוד Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools)
