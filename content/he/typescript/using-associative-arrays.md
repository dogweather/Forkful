---
title:                "שימוש במערכים אסוציאטיביים"
aliases:
- he/typescript/using-associative-arrays.md
date:                  2024-01-30T19:13:56.773392-07:00
model:                 gpt-4-0125-preview
simple_title:         "שימוש במערכים אסוציאטיביים"

tag:                  "Data Structures"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/typescript/using-associative-arrays.md"
changelog:
  - 2024-01-30, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## מה ולמה?

מערכי שיוך, או אובייקטים ב-TypeScript, מאפשרים לכם להשתמש במחרוזות (או מפתחות) כדי לגשת לזוגות ערך. מתכנתים משתמשים בהם לתבניות גישה לנתונים יותר דינמיות בהשוואה למערכים מסורתיים, ומספקים דרך גמישה למבנה וגישה לנתונים ללא צורך להיות קשורים לאינדקסים מספריים.

## איך לעשות:

יצירה ושימוש במערכי שיוך ב-TypeScript היא תהליך ישיר. הנה סקירה בסיסית:

```TypeScript
// הצהרה על מערך שיוך
let user: { [key: string]: string } = {};

// הוספת נתונים
user["name"] = "Jane Doe";
user["email"] = "jane@example.com";

console.log(user);
```

פלט:

```TypeScript
{ name: 'Jane Doe', email: 'jane@example.com' }
```

לדרוך על זוגות מפתח-ערך גם כן קל:

```TypeScript
for (let key in user) {
    console.log(key + ": " + user[key]);
}
```

פלט:

```TypeScript
name: Jane Doe
email: jane@example.com
```

ואם אתם מתמודדים עם סוגי נתונים מעורבים, מערכת הטיפוסים של TypeScript מתגלה כשימושית:

```TypeScript
let mixedTypes: { [key: string]: string | number } = {};
mixedTypes["name"] = "John Doe";
mixedTypes["age"] = 30;

console.log(mixedTypes);
```

פלט:

```TypeScript
{ name: 'John Doe', age: 30 }
```

## צלילה עמוקה

ב-TypeScript, מה שאנו מתייחסים אליו כמערכי שיוך הם למעשה אובייקטים. מבחינה היסטורית, בשפות כמו PHP, מערכי שיוך הם סוג בסיסי, אך JavaScript (ובהרחבה, TypeScript) משתמשת באובייקטים למטרה זו. גישה זו היא גם חוזק וגם הגבלה. אובייקטים מספקים מבנה דינמי ביותר לשיוך מחרוזות לערכים, אך הם אינם מיועדים לשימוש כמערכים במובן המסורתי. לדוגמה, לא ניתן להשתמש בשיטות מערך כמו `push` או `pop` ישירות על אובייקטים אלו.

למקרים בהם יש צורך באוספים מסודרים של זוגות מפתח-ערך עם פעולות דמויות מערך, TypeScript (וה-JavaScript המודרני) מציעה את האובייקט `Map`:

```TypeScript
let userMap = new Map<string, string>();
userMap.set("name", "Jane Doe");
userMap.set("email", "jane@example.com");

userMap.forEach((value, key) => {
    console.log(key + ": " + value);
});
```

תוך כדי שמערכת הטיפוסים של TypeScript ותכונות ES6 כמו `Map` מספקות חלופות עוצמתיות, הבנה של כיצד להשתמש באובייקטים כמערכי שיוך שימושית לתרחישים שבהם אובייקטים ליטרליים הם יעילים יותר או כאשר עובדים עם מבני נתונים של JSON. הכול עניין של בחירה בכלי הנכון למשימה.
