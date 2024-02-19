---
aliases:
- /he/c/working-with-yaml/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:14:29.404884-07:00
description: "YAML, \u05E9\u05E2\u05D5\u05DE\u05D3 \u05DC-\"YAML Ain't Markup Language,\"\
  \ \u05D4\u05D5\u05D0 \u05EA\u05E7\u05DF \u05E1\u05D9\u05D3\u05D5\u05E8 \u05E0\u05EA\
  \u05D5\u05E0\u05D9\u05DD \u05E7\u05E8\u05D9\u05D0 \u05DC\u05D0\u05D3\u05DD \u05E9\
  \u05E0\u05D9\u05EA\u05DF \u05DC\u05D4\u05E9\u05EA\u05DE\u05E9 \u05D1\u05D5 \u05DC\
  \u05DE\u05D2\u05D5\u05D5\u05DF \u05D9\u05D9\u05E9\u05D5\u05DE\u05D9\u05DD, \u05D4\
  \u05D7\u05DC \u05DE\u05E7\u05D1\u05E6\u05D9 \u05EA\u05E6\u05D5\u05E8\u05D4 \u05D5\
  \u05E2\u05D3 \u05D0\u05D7\u05E1\u05D5\u05DF \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD\
  . \u05EA\u05D5\u05DB\u05E0\u05D9\u05EA\u05E0\u05D9\u05DD\u2026"
lastmod: 2024-02-18 23:08:53.366001
model: gpt-4-0125-preview
summary: "YAML, \u05E9\u05E2\u05D5\u05DE\u05D3 \u05DC-\"YAML Ain't Markup Language,\"\
  \ \u05D4\u05D5\u05D0 \u05EA\u05E7\u05DF \u05E1\u05D9\u05D3\u05D5\u05E8 \u05E0\u05EA\
  \u05D5\u05E0\u05D9\u05DD \u05E7\u05E8\u05D9\u05D0 \u05DC\u05D0\u05D3\u05DD \u05E9\
  \u05E0\u05D9\u05EA\u05DF \u05DC\u05D4\u05E9\u05EA\u05DE\u05E9 \u05D1\u05D5 \u05DC\
  \u05DE\u05D2\u05D5\u05D5\u05DF \u05D9\u05D9\u05E9\u05D5\u05DE\u05D9\u05DD, \u05D4\
  \u05D7\u05DC \u05DE\u05E7\u05D1\u05E6\u05D9 \u05EA\u05E6\u05D5\u05E8\u05D4 \u05D5\
  \u05E2\u05D3 \u05D0\u05D7\u05E1\u05D5\u05DF \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD\
  . \u05EA\u05D5\u05DB\u05E0\u05D9\u05EA\u05E0\u05D9\u05DD\u2026"
title: "\u05E2\u05D1\u05D5\u05D3\u05D4 \u05E2\u05DD YAML"
---

{{< edit_this_page >}}

## מה ולמה?

YAML, שעומד ל-"YAML Ain't Markup Language," הוא תקן סידור נתונים קריא לאדם שניתן להשתמש בו למגוון יישומים, החל מקבצי תצורה ועד אחסון נתונים. תוכניתנים לעיתים קרובות עובדים עם YAML כאשר הם זקוקים לפורמט קל לקריאה וקל לכתיבה עבור קבצי תצורה או החלפת נתונים בין שפות ומערכות.

## איך לעשות:

עבודה עם YAML ב-C דורשת ספרייה, שכן הספרייה הסטנדרטית של C אינה מספקת תמיכה ישירה לפירסום או ניתוח YAML. אחת מספריות ה-YAML הפופולריות ביותר עבור C היא `libyaml`, שמציעה ממשקים ברמה נמוכה וברמה גבוהה לניתוח והפקת YAML. להלן דוגמה איך לנתח קובץ YAML פשוט באמצעות `libyaml`:

**ראשית**, עליך להתקין את ספריית ה-`libyaml`. אם אתה נמצא במערכת דומה ל-Unix, בדרך כלל תוכל להתקין אותה דרך מנהל החבילות שלך. לדוגמה, באובונטו:

```bash
sudo apt-get install libyaml-dev
```

**לאחר מכן**, שקול קובץ YAML פשוט בשם `config.yaml`:

```yaml
name: John Doe
age: 29
married: false
```

**הנה** דוגמה בסיסית איך לנתח את קובץ YAML זה ב-C:

```c
#include <yaml.h>
#include <stdio.h>
#include <stdlib.h>

void process_yaml_file(const char *filename) {
    FILE *fh = fopen(filename, "rb");
    yaml_parser_t parser;
    yaml_event_t event;

    if (!yaml_parser_initialize(&parser))
        fputs("Failed to initialize YAML parser!\n", stderr);

    if (fh == NULL)
        fputs("Failed to open file!\n", stderr);

    yaml_parser_set_input_file(&parser, fh);

    while (1) {
        if (!yaml_parser_parse(&parser, &event))
            break;

        if (event.type == YAML_SCALAR_EVENT) {
            printf("Value: %s\n", event.data.scalar.value);
        }

        if (event.type == YAML_STREAM_END_EVENT)
            break;

        yaml_event_delete(&event);
    }

    yaml_parser_delete(&parser);
    fclose(fh);
}

int main() {
    process_yaml_file("config.yaml");
    return 0;
}
```

תוכנית פשוטה זו פותחת קובץ YAML, מאתחלת את מנתח ה-YAML, וקוראת את הקובץ, מדפיסה את ערכי הסקלר (בדוגמה זו, השדות של ה-YAML הפשוט שלנו). שים לב שבדיקת השגיאות היא מינימלית בדוגמה פשוטה זו וצריכה להיות יותר מבוססת בקוד ייצור.

הרצת התוכנית עם ה-`config.yaml` שלנו תפיק:

```plaintext
Value: John Doe
Value: 29
Value: false
```

## ניתוח מעמיק

YAML פורסם לראשונה ב-2001 ותוכנן להיות יותר קריא ונוח למשתמש מאשר פורמטים אחרים של סידור נתונים כמו XML או JSON, תוך שאב השראה ממספר שפות כמו C, Perl, ו-Python לפילוסופיית העיצוב שלו. למרות היתרונות שלו בקריאות ובקלות התיקונים על ידי אנשים, ניתוח YAML באופן תכנותי יכול להיות מורכב בזכות ההתמכות שלו בהזחה ובסט התכונות הרחב שלו, כולל הפניות וטיפוסים מותאמים אישית.

למרות ש-`libyaml` מספקת גישה מוצקה וברמה נמוכה לניתוח והפקת YAML ב-C, היא עשויה להיות מסורבלת למשימות פשוטות בזכות ה-API המפורט שלה. מסיבות אלו, חלק מהמתכנתים מעדיפים להשתמש בספריות ברמה גבוהה יותר או אפילו בפורמטים אחרים של סידור נתונים כמו JSON כאשר הם עובדים ב-C, במיוחד כאשר ניתוח ביצועים עם עודף קוד מינימלי הוא עדיפות. עם זאת, YAML נשאר בחירה פופולרית עבור קבצי תצורה ומצבים שבהם קריאות האדם מהווה עדיפות עליונה. אלטרנטיבות כמו TinyYAML או הטמעת מפרש ברמה גבוהה (למשל, הטמעת Python או Lua) עשויות לספק נוחות רבה יותר ליישומים ספציפיים, מאזנות בין נוחות השימוש לבין צרכי הביצועים.
