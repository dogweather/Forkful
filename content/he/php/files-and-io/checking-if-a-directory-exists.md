---
aliases:
- /he/php/checking-if-a-directory-exists/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:09:03.286428-07:00
description: "\u05D1\u05D3\u05D9\u05E7\u05D4 \u05D0\u05DD \u05EA\u05D9\u05E7\u05D9\
  \u05D9\u05D4 \u05E7\u05D9\u05D9\u05DE\u05EA \u05D4\u05D9\u05D0 \u05DE\u05E9\u05D9\
  \u05DE\u05D4 \u05D9\u05E1\u05D5\u05D3\u05D9\u05EA \u05D1\u05EA\u05DB\u05E0\u05D5\
  \u05EA PHP, \u05E9\u05DB\u05DF \u05D4\u05D9\u05D0 \u05DE\u05D0\u05E4\u05E9\u05E8\
  \u05EA \u05DC\u05DA \u05DC\u05D0\u05DE\u05EA \u05D0\u05EA \u05E0\u05D5\u05DB\u05D7\
  \u05D5\u05EA\u05D4 \u05E9\u05DC \u05EA\u05D9\u05E7\u05D9\u05D9\u05D4 \u05DC\u05E4\
  \u05E0\u05D9 \u05D1\u05D9\u05E6\u05D5\u05E2 \u05E4\u05E2\u05D5\u05DC\u05D5\u05EA\
  \ \u05DB\u05DE\u05D5 \u05E7\u05E8\u05D9\u05D0\u05D4 \u05DE\u05EA\u05D5\u05DA \u05D4\
  \u05E7\u05D1\u05E6\u05D9\u05DD \u05E9\u05D1\u05D4 \u05D0\u05D5 \u05DB\u05EA\u05D9\
  \u05D1\u05D4 \u05D0\u05DC\u05D9\u05D4\u05DD.\u2026"
lastmod: 2024-02-18 23:08:52.946934
model: gpt-4-0125-preview
summary: "\u05D1\u05D3\u05D9\u05E7\u05D4 \u05D0\u05DD \u05EA\u05D9\u05E7\u05D9\u05D9\
  \u05D4 \u05E7\u05D9\u05D9\u05DE\u05EA \u05D4\u05D9\u05D0 \u05DE\u05E9\u05D9\u05DE\
  \u05D4 \u05D9\u05E1\u05D5\u05D3\u05D9\u05EA \u05D1\u05EA\u05DB\u05E0\u05D5\u05EA\
  \ PHP, \u05E9\u05DB\u05DF \u05D4\u05D9\u05D0 \u05DE\u05D0\u05E4\u05E9\u05E8\u05EA\
  \ \u05DC\u05DA \u05DC\u05D0\u05DE\u05EA \u05D0\u05EA \u05E0\u05D5\u05DB\u05D7\u05D5\
  \u05EA\u05D4 \u05E9\u05DC \u05EA\u05D9\u05E7\u05D9\u05D9\u05D4 \u05DC\u05E4\u05E0\
  \u05D9 \u05D1\u05D9\u05E6\u05D5\u05E2 \u05E4\u05E2\u05D5\u05DC\u05D5\u05EA \u05DB\
  \u05DE\u05D5 \u05E7\u05E8\u05D9\u05D0\u05D4 \u05DE\u05EA\u05D5\u05DA \u05D4\u05E7\
  \u05D1\u05E6\u05D9\u05DD \u05E9\u05D1\u05D4 \u05D0\u05D5 \u05DB\u05EA\u05D9\u05D1\
  \u05D4 \u05D0\u05DC\u05D9\u05D4\u05DD.\u2026"
title: "\u05D1\u05D3\u05D9\u05E7\u05D4 \u05D0\u05DD \u05E1\u05E4\u05E8\u05D9\u05D9\
  \u05D4 \u05E7\u05D9\u05D9\u05DE\u05EA"
---

{{< edit_this_page >}}

## מה ולמה?

בדיקה אם תיקייה קיימת היא משימה יסודית בתכנות PHP, שכן היא מאפשרת לך לאמת את נוכחותה של תיקייה לפני ביצוע פעולות כמו קריאה מתוך הקבצים שבה או כתיבה אליהם. פעולה זו עוזרת למנוע שגיאות שעשויות להתרחש בעקבות ניסיון לגשת לתיקיות שאינן קיימות וחיונית לניהול קבצים דינמי בתוך האפליקציות שלך.

## איך לעשות:

הדרך המקורית לבדוק אם תיקייה קיימת ב-PHP היא באמצעות הפונקציה `is_dir()`. פונקציה זו לוקחת נתיב לקובץ כפרמטר ומחזירה `true` אם התיקייה קיימת והיא תיקייה, או `false` במקרה ההפוך.

```php
$directoryPath = "/path/to/your/directory";

if(is_dir($directoryPath)) {
    echo "The directory exists.";
} else {
    echo "The directory does not exist.";
}
```

תצוגה מקדימה של הפלט:
```
The directory exists.
```
או, אם התיקייה לא קיימת:
```
The directory does not exist.
```

למרות שספריית התקנים של PHP מספיק עמידה לרוב משימות התכנות וההפעלה של קבצים ותיקיות, לפעמים עשוי להיות צורך בפתרון יותר מקיף. למקרים כאלה, ספרייה חיצונית פופולרית היא רכיב ה-filesystem של Symfony. הוא מציע מגוון רחב של כלים לניהול מערכת קבצים, כולל דרך פשוטה לבדוק אם תיקייה קיימת.

ראשית, יהיה עליך להתקין את רכיב ה-filesystem של Symfony. אם אתה משתמש ב-Composer (מנהל תלות ל-PHP), תוכל להריץ את הפקודה הבאה בתיקיית הפרויקט שלך:

```
composer require symfony/filesystem
```

לאחר התקנת רכיב ה-filesystem של Symfony, תוכל להשתמש בו כדי לבדוק אם תיקייה קיימת כך:

```php
use Symfony\Component\Filesystem\Filesystem;

$filesystem = new Filesystem();
$directoryPath = '/path/to/your/directory';

if($filesystem->exists($directoryPath)) {
    echo "The directory exists.";
} else {
    echo "The directory does not exist.";
}
```

תצוגה מקדימה של הפלט:
```
The directory exists.
```
או, אם התיקייה לא קיימת:
```
The directory does not exist.
```

שתי השיטות מספקות דרכים אמינות לבדוק את קיומה של תיקייה ב-PHP. הבחירה בין שימוש בפונקציות הפנימיות של PHP או בספרייה חיצונית כמו רכיב ה-filesystem של Symfony תלויה בצרכים הספציפיים של הפרויקט שלך ובשאלה אם אתה זקוק להפעלות נוספות של מערכת הקבצים שיכולות להיות מנוהלות ביעילות רבה יותר על ידי הספרייה.
