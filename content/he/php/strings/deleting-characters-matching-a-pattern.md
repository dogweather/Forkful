---
aliases:
- /he/php/deleting-characters-matching-a-pattern/
date: 2024-01-20 17:42:54.760048-07:00
description: "\u05E2\u05DD \u05E4\u05D5\u05E0\u05E7\u05E6\u05D9\u05D5\u05EA \u05DB\
  \u05DE\u05D5 `preg_replace`, \u05D0\u05E0\u05D7\u05E0\u05D5 \u05DE\u05D5\u05D7\u05E7\
  \u05D9\u05DD \u05EA\u05D5\u05D5\u05D9\u05DD \u05E9\u05DE\u05EA\u05D0\u05D9\u05DE\
  \u05D9\u05DD \u05DC\u05EA\u05D1\u05E0\u05D9\u05EA \u05DE\u05E1\u05D5\u05D9\u05DE\
  \u05EA. \u05D6\u05D4 \u05E9\u05D9\u05DE\u05D5\u05E9\u05D9 \u05DC\u05E0\u05D9\u05E7\
  \u05D5\u05D9 \u05E7\u05DC\u05D8\u05D9\u05DD, \u05D0\u05D9\u05DE\u05D5\u05EA \u05E0\
  \u05EA\u05D5\u05E0\u05D9\u05DD \u05D5\u05E2\u05D9\u05D1\u05D5\u05D3 \u05D8\u05E7\
  \u05E1\u05D8."
lastmod: 2024-02-18 23:08:52.915375
model: gpt-4-1106-preview
summary: "\u05E2\u05DD \u05E4\u05D5\u05E0\u05E7\u05E6\u05D9\u05D5\u05EA \u05DB\u05DE\
  \u05D5 `preg_replace`, \u05D0\u05E0\u05D7\u05E0\u05D5 \u05DE\u05D5\u05D7\u05E7\u05D9\
  \u05DD \u05EA\u05D5\u05D5\u05D9\u05DD \u05E9\u05DE\u05EA\u05D0\u05D9\u05DE\u05D9\
  \u05DD \u05DC\u05EA\u05D1\u05E0\u05D9\u05EA \u05DE\u05E1\u05D5\u05D9\u05DE\u05EA\
  . \u05D6\u05D4 \u05E9\u05D9\u05DE\u05D5\u05E9\u05D9 \u05DC\u05E0\u05D9\u05E7\u05D5\
  \u05D9 \u05E7\u05DC\u05D8\u05D9\u05DD, \u05D0\u05D9\u05DE\u05D5\u05EA \u05E0\u05EA\
  \u05D5\u05E0\u05D9\u05DD \u05D5\u05E2\u05D9\u05D1\u05D5\u05D3 \u05D8\u05E7\u05E1\
  \u05D8."
title: "\u05DE\u05D7\u05D9\u05E7\u05EA \u05EA\u05D5\u05D5\u05D9\u05DD \u05D4\u05EA\
  \u05D5\u05D0\u05DE\u05D9\u05DD \u05DC\u05EA\u05D1\u05E0\u05D9\u05EA"
---

{{< edit_this_page >}}

## מה ולמה?
עם פונקציות כמו `preg_replace`, אנחנו מוחקים תווים שמתאימים לתבנית מסוימת. זה שימושי לניקוי קלטים, אימות נתונים ועיבוד טקסט.

## איך לעשות:
```PHP
$text = "שלום! האם למחוק את הסימנים המיוחדים #@$?";
$pattern = '/[#!@$%&*()]/'; // דפוס למחיקה
$clean_text = preg_replace($pattern, '', $text);
echo $clean_text; // תוצאה: "שלום האם למחוק את הסימנים המיוחדים "
```
אפשר גם למחוק תווים בתחומים של ASCII:
```PHP
$text = "Numbers 123, symbols @#₪!, and English abCD";
$pattern = '/[^א-ת ]/'; // [^א-ת ] מתאים לכל דבר שלא תווים בעברית ורווחים
$hebrew_text = preg_replace($pattern, '', $text);
echo $hebrew_text; // תוצאה: " ו"
```

## עיון מעמיק
`preg_replace` מבוססת על ביטויים רגולריים, טכנולוגיה שחלק מהיסודות שלה החלו בשנות ה-50. אלטרנטיבות פשוטות יותר כמו `str_replace` מתאימות למחיקת תווים ספציפיים, אבל לא לתבניות. יש להתייחס לביטויים רגולריים בזהירות כי שגיאה קטנה יכולה לגרום לתוצאות בלתי צפויות או אפילו לתקלות ביצוע.

## ראה גם
- [PHP Manual on preg_replace](https://www.php.net/manual/en/function.preg-replace.php)
- [Regular Expressions Intro](https://www.regular-expressions.info/)
- [PHP Manual on str_replace](https://www.php.net/manual/en/function.str-replace.php)
- [PHP The Right Way - Regular Expressions](https://phptherightway.com/#regular_expressions)
