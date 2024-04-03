---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:54:59.113468-07:00
description: "\u05D0\u05D9\u05D7\u05D5\u05D3 \u05DE\u05D7\u05E8\u05D5\u05D6\u05D5\u05EA\
  \ \u05D1\u05E9\u05E4\u05EA C \u05DE\u05E9\u05DE\u05E9 \u05DC\u05D7\u05D9\u05D1\u05D5\
  \u05E8 \u05E9\u05EA\u05D9 \u05DE\u05D7\u05E8\u05D5\u05D6\u05D5\u05EA \u05D0\u05D5\
  \ \u05D9\u05D5\u05EA\u05E8 \u05D6\u05D5 \u05DC\u05D6\u05D5 \u05DB\u05D3\u05D9 \u05DC\
  \u05D9\u05E6\u05D5\u05E8 \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05D7\u05D3\u05E9\
  \u05D4. \u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05DE\u05D1\u05E6\u05E2\u05D9\
  \u05DD \u05E4\u05E2\u05D5\u05DC\u05D4 \u05D6\u05D5 \u05DB\u05D3\u05D9 \u05DC\u05D1\
  \u05E0\u05D5\u05EA \u05D1\u05D0\u05D5\u05E4\u05DF \u05D3\u05D9\u05E0\u05DE\u05D9\
  \ \u05DE\u05D7\u05E8\u05D5\u05D6\u05D5\u05EA \u05D1\u05D6\u05DE\u05DF \u05E8\u05D9\
  \u05E6\u05D4, \u05D4\u05DB\u05E8\u05D7\u05D9\u2026"
lastmod: '2024-03-13T22:44:40.109913-06:00'
model: gpt-4-0125-preview
summary: "\u05D0\u05D9\u05D7\u05D5\u05D3 \u05DE\u05D7\u05E8\u05D5\u05D6\u05D5\u05EA\
  \ \u05D1\u05E9\u05E4\u05EA C \u05DE\u05E9\u05DE\u05E9 \u05DC\u05D7\u05D9\u05D1\u05D5\
  \u05E8 \u05E9\u05EA\u05D9 \u05DE\u05D7\u05E8\u05D5\u05D6\u05D5\u05EA \u05D0\u05D5\
  \ \u05D9\u05D5\u05EA\u05E8 \u05D6\u05D5 \u05DC\u05D6\u05D5 \u05DB\u05D3\u05D9 \u05DC\
  \u05D9\u05E6\u05D5\u05E8 \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05D7\u05D3\u05E9\
  \u05D4."
title: "\u05D7\u05D9\u05D1\u05D5\u05E8 \u05DE\u05D7\u05E8\u05D5\u05D6\u05D5\u05EA"
weight: 3
---

## איך לעשות:
ב-C, מחרוזות הן מערכים של תווים הנגמרים בתו נול (`\0`). בניגוד לשפות ברמה גבוהה יותר, C לא מספקת פונקציה מובנית לאיחוד מחרוזות. במקום זאת, משתמשים בפונקציות `strcat()` או `strncat()` מהספרייה `<string.h>`.

הנה דוגמה פשוטה באמצעות `strcat()`:

```c
#include <stdio.h>
#include <string.h>

int main() {
    char destination[50] = "Hello, ";
    char source[] = "World!";

    strcat(destination, source);

    printf("%s\n", destination);  // פלט: Hello, World!
    return 0;
}
```

הפונקציה `strcat()` לוקחת שני ארגומנטים: מחרוזת יעד (שחייבת לכלול מספיק מקום לאחסן את התוצאה המאוחדת) ומחרוזת מקור. לאחר מכן היא מוסיפה את מחרוזת המקור למחרוזת היעד.

לשליטה טובה יותר על מספר התווים המאוחדים, `strncat()` היא בטוחה יותר לשימוש:

```c
#include <stdio.h>
#include <string.h>

int main() {
    char destination[50] = "Hello, ";
    char source[] = "World!";
    int num = 3; // מספר התווים להוספה

    strncat(destination, source, num);

    printf("%s\n", destination);  // פלט: Hello, Wor
    return 0;
}
```

הדבר מגביל את האיחוד ל-`num` התווים הראשונים של מחרוזת המקור, ועוזר למנוע גלישת חוצץ.

## צלילה עמוקה
הפונקציות `strcat()` ו-`strncat()` היו חלק מספריית התקן של C מאז היווסדה, משקפות את האופי הנמוך של השפה שדורשת ניהול ידני של מחרוזות וזיכרון. בניגוד לשפות תכנות מודרניות רבות שמתייחסות למחרוזות כאובייקטים מכובדים עם אופרטורים מובנים לאיחוד (כמו `+` או `.concat()`), גישת C דורשת הבנה עמוקה יותר של מצביעים, הקצאת זיכרון, וסכנות פוטנציאליות כמו גלישת חוצץ.

למרות ש-`strcat()` ו-`strncat()` נמצאות בשימוש נרחב, הן לעיתים קרובות נמצאות תחת ביקורת בשל הפוטנציאל שלהן ליצירת אי-התאמות ביטחון אם לא ישתמשו בהן בזהירות. גלישות חוצץ, שבהן נתונים חורגים מהזיכרון המוקצה, יכולות להוביל להתרסקויות או לניצול לביצוע קוד שרירותי. כתוצאה מכך, מתכנתים הולכים ומעדיפים חלופות בטוחות יותר, כמו `snprintf()`, שמספקת התנהגות נבונה יותר על ידי הגבלת מספר התווים הנכתבים למחרוזת היעד בהתבסס על גודלה:

```c
char destination[50] = "Hello, ";
char source[] = "World!";
snprintf(destination + strlen(destination), sizeof(destination) - strlen(destination), "%s", source);
```

השיטה הזו היא ארוכה יותר אך הרבה יותר בטוחה, מדגישה הזזה במחשבה בתכנות C לעבר יעדים של ביטחון ועמידות על פני תמציתיות.

למרות האתגרים האלה, איחוד מחרוזות ב-C הוא כישור יסודי, חיוני לתכנות יעיל בשפה. הבנת ההפשטות והסיכונים הקשורים היא מפתח לשליטה בתכנות C.
