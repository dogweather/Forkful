---
aliases:
- /he/php/starting-a-new-project/
date: 2024-01-20 18:04:22.422583-07:00
description: "\u05E4\u05EA\u05D9\u05D7\u05EA \u05E4\u05E8\u05D5\u05D9\u05E7\u05D8\
  \ \u05D7\u05D3\u05E9 \u05D1-PHP \u05D6\u05D4 \u05EA\u05D4\u05DC\u05D9\u05DA \u05E9\
  \u05DC \u05D4\u05E7\u05DE\u05EA \u05E1\u05D1\u05D9\u05D1\u05EA \u05E4\u05D9\u05EA\
  \u05D5\u05D7 \u05DE\u05EA\u05D0\u05D9\u05DE\u05D4 \u05DC\u05D1\u05E0\u05D9\u05D9\
  \u05EA \u05DE\u05E9\u05D4\u05D5 \u05D7\u05D3\u05E9. \u05EA\u05DB\u05E0\u05EA\u05D9\
  \u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9 \u05DC\
  \u05D9\u05E6\u05D5\u05E8 \u05DE\u05D5\u05E6\u05E8\u05D9\u05DD \u05D7\u05D3\u05E9\
  \u05D9\u05DD, \u05DC\u05DC\u05DE\u05D5\u05D3, \u05D5\u05DC\u05E4\u05EA\u05D5\u05E8\
  \ \u05D1\u05E2\u05D9\u05D5\u05EA."
lastmod: 2024-02-18 23:08:52.932452
model: gpt-4-1106-preview
summary: "\u05E4\u05EA\u05D9\u05D7\u05EA \u05E4\u05E8\u05D5\u05D9\u05E7\u05D8 \u05D7\
  \u05D3\u05E9 \u05D1-PHP \u05D6\u05D4 \u05EA\u05D4\u05DC\u05D9\u05DA \u05E9\u05DC\
  \ \u05D4\u05E7\u05DE\u05EA \u05E1\u05D1\u05D9\u05D1\u05EA \u05E4\u05D9\u05EA\u05D5\
  \u05D7 \u05DE\u05EA\u05D0\u05D9\u05DE\u05D4 \u05DC\u05D1\u05E0\u05D9\u05D9\u05EA\
  \ \u05DE\u05E9\u05D4\u05D5 \u05D7\u05D3\u05E9. \u05EA\u05DB\u05E0\u05EA\u05D9\u05DD\
  \ \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9 \u05DC\u05D9\
  \u05E6\u05D5\u05E8 \u05DE\u05D5\u05E6\u05E8\u05D9\u05DD \u05D7\u05D3\u05E9\u05D9\
  \u05DD, \u05DC\u05DC\u05DE\u05D5\u05D3, \u05D5\u05DC\u05E4\u05EA\u05D5\u05E8 \u05D1\
  \u05E2\u05D9\u05D5\u05EA."
title: "\u05D4\u05EA\u05D7\u05DC\u05EA \u05E4\u05E8\u05D5\u05D9\u05E7\u05D8 \u05D7\
  \u05D3\u05E9"
---

{{< edit_this_page >}}

## מה ולמה?

פתיחת פרויקט חדש ב-PHP זה תהליך של הקמת סביבת פיתוח מתאימה לבניית משהו חדש. תכנתים עושים זאת כדי ליצור מוצרים חדשים, ללמוד, ולפתור בעיות.

## איך לעשות:

כדי להתחיל, תצטרך להגדיר בסיס לפרויקט שלך. בואו נראה איך אפשר להקים פרויקט PHP פשוט.

```PHP
<?php
// התחברות למערכת מנהל החבילות Composer.
require 'vendor/autoload.php';

// יצירת קובץ index.php.
echo 'שלום עולם!';

// אל תשכח להריץ: composer install
?>
```
פלט לדוגמה:
```
שלום עולם!
```

## עיון מעמיק:

Composer הוא מנהל חבילות פופולרי ב-PHP, שמשמש לניהול תלותיות של פרויקט. פותח ב-2012, והוא חלק בלתי נפרד מהקהילה. ישנם אלטרנטיבות, כמו PEAR, אבל Composer הוא הבחירה העכשווית. כשאתה מתחיל פרויקט חדש, חשוב להבין איך להשתמש בממשק הפקודות של Composer ואיך לטפל בקובץ `composer.json`. וגם, זה סופר חשוב לקיים רגלי אבטחה טובים, דוגמת יישום CSRF ו-XSS.

## נוסף על כך:

- [PHP The Right Way](https://phptherightway.com/) - מדריך עכשווי ומלא רעיונות ל PHP.
- [Composer](https://getcomposer.org/) - האתר הרשמי של מנהל החבילות Composer.
- [Packagist](https://packagist.org/) - האוסף חבילות הרשמי של Composer.
- [PHP Fig](https://www.php-fig.org/) - קבוצת PHP Framework Interop Group שמוציאה את PSR, כללים לכתיבת קוד PHP בצורה סטנדרטית.
