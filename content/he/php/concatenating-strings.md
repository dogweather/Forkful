---
title:                "חיבור מחרוזות"
html_title:           "C++: חיבור מחרוזות"
simple_title:         "חיבור מחרוזות"
programming_language: "PHP"
category:             "PHP"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/php/concatenating-strings.md"
---

{{< edit_this_page >}}

## מה & למה?

השרשור של מחרוזות הוא האזרח הכאבל לדביקה של שני או יותר מחרוזות ב- PHP. מתכנתים מבצעים שרשור כדי ליצור מחרוזת רציפה, להתאים שמות לנתונים, או לחליפין שימוש בפונקציות וקבועים.

## איך:

הנה כמה דוגמאות לשימוש באופרטור שרשור (.):

```PHP
<?php
$str1 = 'שלום, ';
$str2 = 'עולם!';
$greeting = $str1 . $str2;
echo $greeting;  // תוצאה: "שלום, עולם!"
?>
```

אנחנו יכולים גם לעשות שרשור ישיר למשתנה עם השימוש באופרטור `.= `. 

```PHP
<?php
$str = 'שלום, ';
$str .= 'עולם!';
echo $str;  // תוצאה: "שלום, עולם!"
?>
```

## צלילה עמוקה

האופרטור לשרשור המחרוזתים נחשב לאחד מהאופרטורים הבסיסיים ב- PHP והוא נמצא בשימוש מהגרסה הראשונה של PHP. מכיוון ש- PHP היא שפה מונחת מחרוזת, הקיומות של אופרטור שרשור הוא מרכזי.

כלפי מטה שני אלטרנטיבות לשרשור מחרוזות ב- PHP:

1. שימוש בפונקציה `sprintf()`:
   ```PHP
   <?php
   $greeting = sprintf('%s %s', 'שלום,', 'עולם!');
   echo $greeting;  // תוצאה: "שלום, עולם!"
   ?>
   ```
2. שימוש בתחביר של מחרוזת משולבת (`interpolation syntax`):
   ```PHP
   <?php
   $world = 'עולם!';
   echo "שלום, $world";  // תוצאה: "שלום, עולם!"
   ?>
   ```

## ראו גם

1. [המתיחה למתנדבים בחרוזות של PHP ב- PHP Manual](https://www.php.net/manual/he/language.operators.string.php)
2. [המחרוזת של הפונקציות ב- PHP Manual](https://www.php.net/manual/he/book.strings.php)