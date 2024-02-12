---
title:                "הסרת מרכאות מתוך מחרוזת"
aliases:
- /he/c/removing-quotes-from-a-string/
date:                  2024-02-03T18:07:50.392501-07:00
model:                 gpt-4-0125-preview
simple_title:         "הסרת מרכאות מתוך מחרוזת"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/c/removing-quotes-from-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## מה ולמה?

הסרת מרכאות ממחרוזת ב-C כוללת את חילוץ התוכן הטקסטואלי ללא המרכאות המקיפות בודדות (' ') או כפולות (" "). תהליך זה הכרחי לסננת נתוני קלט, ניתוח תוכן קבצים, או הכנת מחרוזות לעיבוד נוסף שבו המרכאות אינן נדרשות או עלולות להוביל לשגיאות בטיפול בנתונים.

## איך לעשות:

כדי להסיר מרכאות ממחרוזת ב-C, אנו עוברים על המחרוזת, ומעתיקים תווים שאינם מרכאות למחרוזת חדשה. תהליך זה ניתן להתאמה להסרה של המרכאות המובילות והסופיות בלבד או של כל המרכאות הקיימות במחרוזת. להלן דוגמא אילוסטרטיבית המדגימה את שתי הגישות:

```c
#include <stdio.h>
#include <string.h>

// פונקציה להסרת כל המרכאות ממחרוזת
void removeAllQuotes(char *source, char *dest) {
    while (*source) {
        if (*source != '"' && *source != '\'') {
            *dest++ = *source;
        }
        source++;
    }
    *dest = '\0'; // סיום המחרוזת היעד ב-NULL
}

// פונקציה להסרת המרכאות המובילות והסופיות ממחרוזת
void removeEdgeQuotes(char *source, char *dest) {
    size_t len = strlen(source);
    if (source[0] == '"' || source[0] == '\'') source++, len--;
    if (source[len-1] == '"' || source[len-1] == '\'') len--;
    strncpy(dest, source, len);
    dest[len] = '\0'; // סיום המחרוזת היעד ב-NULL
}

int main() {
    char str1[] = "'Hello, World!'";
    char str2[] = "\"Programming in C\"";
    char noQuotes1[50];
    char noQuotes2[50];
    
    removeAllQuotes(str1, noQuotes1);
    printf("All Quotes Removed: %s\n", noQuotes1);
    
    removeEdgeQuotes(str2, noQuotes2);
    printf("Edge Quotes Removed: %s\n", noQuotes2);
    
    return 0;
}
```
פלט לדוגמא:
```
All Quotes Removed: Hello, World!
Edge Quotes Removed: Programming in C
```

הדוגמאות הללו מראות איך לטפל הן בהסרת כל המרכאות הקיימות במחרוזת והן בהסרה ממוקדת של המרכאות המובילות והסופיות בלבד.

## צלילה עמוקה

המושג של הסרת מרכאות ממחרוזות אינו מציג עומק היסטורי משמעותי ב-C, מעבר לקשריו לצורכי עיבוד טקסט מוקדמים. הגישה הישירה המוצגת כאן היא גמישה אך חסרת יעילות למחרוזות גדולות מאוד או לדרישות ביצועים גבוהות, שם תיקון במקום או אלגוריתמים מתקדמים יותר עשויים להעדיף.

אלטרנטיבות, כמו שימוש ב-`strpbrk` למציאת מרכאות והזזת החלק שאינו מרכאות של המחרוזת, יכולות להיות יעילות יותר אך דורשות הבנה עמוקה יותר של מצביעים וניהול זיכרון ב-C. יתרה מכך, הופעתו של מערכות ספריות לביטויים רגולריים הציעה ערכת כלים חזקה למניפולציית מחרוזות, כולל הסרת מרכאות. עם זאת, ספריות אלו, למרות שהן חזקות, מוסיפות מורכבות ועומס שעשויים שלא להיות נחוצים למשימות פשוטות יותר. לפיכך, הגישה הישירה כפי שהוצגה, נשארת כישור יקר ערך למתכנתי C, משלבת פשטות עם יעילות למקרים רבים של שימוש רגיל.
