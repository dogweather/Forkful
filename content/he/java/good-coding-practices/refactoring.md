---
date: 2024-01-26 01:40:23.275737-07:00
description: "\u05E8\u05D9\u05E4\u05E7\u05D8\u05D5\u05E8\u05D9\u05E0\u05D2 \u05D4\u05D5\
  \u05D0 \u05EA\u05D4\u05DC\u05D9\u05DA \u05E9\u05DC \u05DE\u05D1\u05E0\u05D4 \u05DE\
  \u05D7\u05D3\u05E9 \u05E9\u05DC \u05E7\u05D5\u05D3 \u05DE\u05D7\u05E9\u05D1 \u05E7\
  \u05D9\u05D9\u05DD - \u05E9\u05D9\u05E0\u05D5\u05D9 \u05D4\u05E4\u05E7\u05D8\u05D5\
  \u05E8\u05D9\u05E0\u05D2 - \u05DE\u05D1\u05DC\u05D9 \u05DC\u05E9\u05E0\u05D5\u05EA\
  \ \u05D0\u05EA \u05D4\u05EA\u05E0\u05D4\u05D2\u05D5\u05EA\u05D5 \u05D4\u05D7\u05D9\
  \u05E6\u05D5\u05E0\u05D9\u05EA. \u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05E2\
  \u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9 \u05DC\u05E9\u05E4\
  \u05E8 \u05D0\u05EA \u05D4\u05EA\u05DB\u05D5\u05E0\u05D5\u05EA \u05D4\u05DC\u05D0\
  \u2026"
lastmod: '2024-03-13T22:44:39.144953-06:00'
model: gpt-4-0125-preview
summary: "\u05E8\u05D9\u05E4\u05E7\u05D8\u05D5\u05E8\u05D9\u05E0\u05D2 \u05D4\u05D5\
  \u05D0 \u05EA\u05D4\u05DC\u05D9\u05DA \u05E9\u05DC \u05DE\u05D1\u05E0\u05D4 \u05DE\
  \u05D7\u05D3\u05E9 \u05E9\u05DC \u05E7\u05D5\u05D3 \u05DE\u05D7\u05E9\u05D1 \u05E7\
  \u05D9\u05D9\u05DD - \u05E9\u05D9\u05E0\u05D5\u05D9 \u05D4\u05E4\u05E7\u05D8\u05D5\
  \u05E8\u05D9\u05E0\u05D2 - \u05DE\u05D1\u05DC\u05D9 \u05DC\u05E9\u05E0\u05D5\u05EA\
  \ \u05D0\u05EA \u05D4\u05EA\u05E0\u05D4\u05D2\u05D5\u05EA\u05D5 \u05D4\u05D7\u05D9\
  \u05E6\u05D5\u05E0\u05D9\u05EA."
title: "\u05E8\u05E4\u05E7\u05D8\u05D5\u05E8\u05D9\u05E0\u05D2"
weight: 19
---

## איך לעשות:
בואו ניקח מחלקת Java פשוטה שצועקת לריפקטורינג בגלל הארגון העני והחוסר בבהירות שלה.

```java
public class Calculator {
    public int calc(int op1, int op2, String operation) {
        if (operation.equals("add")) {
            return op1 + op2;
        } else if (operation.equals("subtract")) {
            return op1 - op2;
        } // פעולות נוספות...
    }
}
```

לאחר הריפקטורינג, יש לנו:

```java
public class Calculator {
    public int add(int operand1, int operand2) {
        return operand1 + operand2;
    }

    public int subtract(int operand1, int operand2) {
        return operand1 - operand2;
    }

    // פעולות נוספות...
}
```

על ידי ריפקטורינג, שיפרנו את שמות הפונקציות והפרמטרים לצורך קריאות והסרנו את הצורך בענף תנאי בתוך פונקציה בודדת. כל פעולה כעת מצהירה במפורש על מטרתה.

## צלילה עמוקה:
ריפקטורינג הוא בעל שורשים בקהילת ה-Smalltalk, עם הדגש על קריאות הקוד ועיצוב מונחה-עצמים, אך הוא באמת פרח בעולם ה-Java בסוף שנות ה-90 ותחילת שנות ה-2000, בפרט לאחר פרסום הספר החשוב של מרטין פאולר, "ריפקטורינג: שיפור עיצוב קוד קיים".

ישנן חלופות לריפקטורינג, כמו כתיבת הקוד מחדש מאפס. עם זאת, ריפקטורינג לעיתים נעדף משום שהוא כולל שינויים הדרגתיים שאינם מפריעים לפונקציונליות של היישום.

פרטי היישום כאשר מבצעים ריפקטורינג ב-Java (או בכל שפת תכנות) כרוכים בהבנת ריחות קוד - אינדיקטורים לבעיות עמוקות יותר בקוד. חלק מהריחות כוללים שיטות ארוכות, מחלקות גדולות, קוד כפול, ושימוש יתר בפרימיטיבים. על ידי החלת דפוסי ריפקטורינג כגון Extract Method, Move Method, או Replace Temp with Query, מפתחים יכולים לטפל באופן מסודר בריחות אלה תוך כדי הבטחת התפקוד התקין של הקוד בכל עת.

כלים אוטומטיים, כמו תמיכת הריפקטורינג של IntelliJ IDEA, או תוספים ל-Eclipse, יכולים לסייע בתהליך על ידי אוטומציה של פעולות ריפקטורינג כמו שינוי שמות של משתנים, שיטות, ומחלקות, חילוץ שיטות או משתנים, והעברת שיטות או מחלקות לחבילות או מרחבי שמות שונים.

## ראה גם:
- ספרו של מרטין פאולר "ריפקטורינג: שיפור עיצוב קוד קיים": https://martinfowler.com/books/refactoring.html
- טכניקות ריפקטורינג ב-Refactoring.Guru: https://refactoring.guru/refactoring/techniques
- ריפקטורינג אוטומטי ב-Eclipse: https://www.eclipse.org/eclipse/news/4.18/jdt.php
- תכונות ריפקטורינג של IntelliJ IDEA: https://www.jetbrains.com/idea/features/refactoring.html

כל אחד מהמשאבים הללו מספק בסיס להבנת עקרונות הריפקטורינג או כלים שניתן להשתמש בהם כדי ליישם את עקרונות אלה בפועל.
