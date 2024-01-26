---
title:                "קבלת התאריך הנוכחי"
date:                  2024-01-20T15:15:44.650984-07:00
html_title:           "C: קבלת התאריך הנוכחי"
simple_title:         "קבלת התאריך הנוכחי"
programming_language: "PHP"
category:             "PHP"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/php/getting-the-current-date.md"
---

{{< edit_this_page >}}

## מה ולמה?
לקבל את התאריך הנוכחי ב-PHP היא פעולה בסיסית - זה מאפשר לך לרשום תאריכים, לבצע פעולות על זמנים ולתייג אירועים. תכניתנים עושים זאת כדי לנהל תחזוקה, לעקוב אחרי זמנים ולהציג מידע מותאם למשתמש.

## איך לעשות:
הנה דרך פשוטה לקבל את התאריך והשעה הנוכחיים:

```php
<?php
echo date("Y-m-d H:i:s");
?>
```

פלט דוגמה:
```
2023-04-05 15:21:34
```

לקבלת תאריך ללא שעה:

```php
<?php
echo date("Y-m-d");
?>
```

פלט דוגמה:
```
2023-04-05
```

## נפילה עמוקה:
PHP משתמשת בפונקציה date() להבאת התאריך והשעה. היא קיימת מאז הגרסה הראשונה של PHP ומשמשת כתקן לתקשורת תאריכים. קיימות אלטרנטיבות כמו קלאס DateTime שמציע יותר גמישות לעיבוד תאריכים וזמנים. לפרטים על הפורמט של המחרוזת שמועברת לפונקציה, כדאי לבדוק במדריך PHP - יש שם אינסוף אפשרויות להתאמה אישית.

## ראה גם:
- [מדריך הפונקציות להצגת תאריך ושעה ב-PHP](https://www.php.net/manual/en/book.datetime.php)
- [מבוא לאובייקט DateTime](https://www.php.net/manual/en/class.datetime.php)
- [מסמכי תקן זמן ותאריך של PHP](https://www.php.net/manual/en/datetime.format.php)
