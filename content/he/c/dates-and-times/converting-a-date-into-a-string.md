---
aliases:
- /he/c/converting-a-date-into-a-string/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:54:37.222928-07:00
description: "\u05D4\u05DE\u05E8\u05EA \u05EA\u05D0\u05E8\u05D9\u05DA \u05DC\u05DE\
  \u05D7\u05E8\u05D5\u05D6\u05EA \u05D1\u05E9\u05E4\u05EA C \u05DB\u05D5\u05DC\u05DC\
  \u05EA \u05D0\u05EA \u05EA\u05E8\u05D2\u05D5\u05DD \u05DE\u05D1\u05E0\u05D4 \u05EA\
  \u05D0\u05E8\u05D9\u05DA \u05D0\u05D5 \u05D7\u05D5\u05EA\u05DE\u05EA \u05D6\u05DE\
  \u05DF \u05DC\u05EA\u05E1\u05D3\u05D9\u05E8 \u05E7\u05E8\u05D9\u05D0 \u05DC\u05D0\
  \u05D3\u05DD. \u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05DC\u05E2\u05D9\u05EA\u05D9\
  \u05DD \u05E7\u05E8\u05D5\u05D1\u05D5\u05EA \u05DE\u05D1\u05E6\u05E2\u05D9\u05DD\
  \ \u05DE\u05E9\u05D9\u05DE\u05D4 \u05D6\u05D5 \u05DB\u05D3\u05D9 \u05DC\u05D4\u05E6\
  \u05D9\u05D2 \u05EA\u05D0\u05E8\u05D9\u05DB\u05D9\u05DD \u05D1\u05D9\u05D5\u05DE\
  \u05E0\u05D9 \u05E8\u05D9\u05E9\u05D5\u05DD,\u2026"
lastmod: 2024-02-18 23:08:53.355658
model: gpt-4-0125-preview
summary: "\u05D4\u05DE\u05E8\u05EA \u05EA\u05D0\u05E8\u05D9\u05DA \u05DC\u05DE\u05D7\
  \u05E8\u05D5\u05D6\u05EA \u05D1\u05E9\u05E4\u05EA C \u05DB\u05D5\u05DC\u05DC\u05EA\
  \ \u05D0\u05EA \u05EA\u05E8\u05D2\u05D5\u05DD \u05DE\u05D1\u05E0\u05D4 \u05EA\u05D0\
  \u05E8\u05D9\u05DA \u05D0\u05D5 \u05D7\u05D5\u05EA\u05DE\u05EA \u05D6\u05DE\u05DF\
  \ \u05DC\u05EA\u05E1\u05D3\u05D9\u05E8 \u05E7\u05E8\u05D9\u05D0 \u05DC\u05D0\u05D3\
  \u05DD. \u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05DC\u05E2\u05D9\u05EA\u05D9\u05DD\
  \ \u05E7\u05E8\u05D5\u05D1\u05D5\u05EA \u05DE\u05D1\u05E6\u05E2\u05D9\u05DD \u05DE\
  \u05E9\u05D9\u05DE\u05D4 \u05D6\u05D5 \u05DB\u05D3\u05D9 \u05DC\u05D4\u05E6\u05D9\
  \u05D2 \u05EA\u05D0\u05E8\u05D9\u05DB\u05D9\u05DD \u05D1\u05D9\u05D5\u05DE\u05E0\
  \u05D9 \u05E8\u05D9\u05E9\u05D5\u05DD,\u2026"
title: "\u05D4\u05DE\u05E8\u05EA \u05EA\u05D0\u05E8\u05D9\u05DA \u05DC\u05DE\u05D7\
  \u05E8\u05D5\u05D6\u05EA"
---

{{< edit_this_page >}}

## מה ולמה?

המרת תאריך למחרוזת בשפת C כוללת את תרגום מבנה תאריך או חותמת זמן לתסדיר קריא לאדם. תכנתים לעיתים קרובות מבצעים משימה זו כדי להציג תאריכים ביומני רישום, ממשקי משתמש, או כאשר מאחסנים תאריכים בפורמט טקסטואלי כמו JSON או CSV.

## איך לעשות:

הפונקציה `strftime` מספריית ה-`<time.h>` משמשת בדרך כלל למטרה זו. היא מאפשרת לך לעצב תאריך ושעה במגוון דרכים על ידי ציון מפרטי פורמט. הנה דוגמה מהירה:

```c
#include <stdio.h>
#include <time.h>

int main() {
    char dateStr[100];
    time_t now = time(NULL);
    struct tm *ptm = localtime(&now);

    // המרת התאריך והשעה למחרוזת (למשל, "Wed Jun 30 21:49:08 2021")
    strftime(dateStr, sizeof(dateStr), "%a %b %d %H:%M:%S %Y", ptm);
    
    printf("התאריך והשעה הנוכחיים: %s\n", dateStr);
    return 0;
}
```

פלט לדוגמה עשוי להיראות כך:

```
התאריך והשעה הנוכחיים: Wed Jun 30 21:49:08 2021
```

ניתן להתאים אישית את הפורמט על ידי שינוי מפרטי הפורמט המועברים ל-`strftime`. לדוגמה, כדי לקבל את התאריך בפורמט `YYYY-MM-DD`, היית משתמש ב-`"%Y-%m-%d"`.

## טבילה עמוקה

הפונקציה `strftime` וספריית ה-`<time.h>` הן חלק מספריית התקנים של שפת C, שחוזרת לתקן אנס"י ה-C המקורי (C89/C90). למרות שגישה זו פשוטה ונתמכת במגוון רחב של פלטפורמות, היא עשויה להיראות נמוכה ומסורבלת לעומת שפות תכנות מודרניות שמציעות ספריות תאריך ושעה יותר אינטואיטיביות.

כדאי לשים לב, על אף שפונקציות הזמן של ספריית התקנים של C נתמכות ברחבי ופשוטות לשימוש, הן חסרות כמה מהמאפיינים המורכבים יותר של ניהול אזורי זמן ואינטרנציונליזציה הנמצאים בספריות של שפות חדשות יותר או בספריות C של צד שלישי כמו International Components for Unicode (ICU).

עם זאת, יכולות ההתאמה האישית של הפונקציה `strftime` והתמיכה הרחבה בפלטפורמות שונות הופכות אותה לכלי אמין ושימושי להמרת מחרוזות תאריך ב-C. תכנתים הבאים משפות עם ספריות תאריך ושעה ברמה גבוהה יותר יצטרכו להסתגל לטבעה הנמוך שלה אך ימצאו אותה עוצמתית ומגוונת במיוחד לעיצוב תאריכים ושעות למגוון יישומים.
