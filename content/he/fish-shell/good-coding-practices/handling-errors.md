---
title:                "טיפול בשגיאות"
aliases:
- /he/fish-shell/handling-errors/
date:                  2024-01-26T00:52:12.241600-07:00
model:                 gpt-4-1106-preview
simple_title:         "טיפול בשגיאות"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/fish-shell/handling-errors.md"
---

{{< edit_this_page >}}

## מה ולמה?
טיפול בשגיאות מאפשר לסקריפט שלך להתמודד עם הלא צפוי בחן. אנו עושים זאת כדי לנהל כשל בלי להפוך את שיערם של המשתמשים שלנו לאפור.

## איך לעשות זאת:
כדי לתפוס שגיאות ב-Fish, נשען על הפקודה `status` ועל תנאיים. נניח ש־`ping` נכשל; הנה איך לזהות זאת:

```fish
ping -c 1 example.com
if not status is-success
    echo "משהו דגיג קרה עם הפינג."
end
```

פלט לדוגמא אם `ping` נכשל:

```
משהו דגיג קרה עם הפינג.
```

כדי לטפל בקוד שגיאה מסוים, השתמש ב־`status --is`:

```fish
false
if status --is 1
    echo "תפסת שגיאה עם קוד 1."
end
```

פלט לדוגמא:
```
תפסת שגיאה עם קוד 1.
```

לגישה יותר מוצקה, שקול להשתמש בפונקציה:

```fish
function try_ping
    ping -c 1 example.com
    or begin
        echo "הפינג נכשל עם מצב $status"
        return 1
    end
end

try_ping
```

## עיון מעמיק
טיפול בשגיאות ב-Fish אינו תואם לפרדיגמת `try/catch` שאתה עשוי להכיר משפות עיליות יותר. במקום זאת, יש לך סטטוסים יציאה ישירים המסופקים על ידי הפקודה `status`.

מבחינה היסטורית, במערכות דמויות Unix, סטטוס יציאה של `0` מציין הצלחה, בעוד כל ערך שאינו אפס מציין שגיאה, שלרוב משקף סיבות כישלון שונות. קונבנציה זו משמשת רוב כלי השורה הפקודה ולכן גם על ידי Fish עצמו.

חלופות לבדיקות `status` ב-Fish כוללות טיפול באותות באמצעות `trap` בשללים אחרים, אך Fish מעדיף בדיקות מצב יותר מפורשות, מכיוון שהן נקיות יותר ופחות נוטות לתופעות לוואי.

מבחינה טכנית, טיפול בשגיאות ב-Fish נשאר פשוט ועדיין עוצמתי, במידה רבה בזכות האופי הלא חוסם שלו ועל הדגש על תחביר ברור, כמו שמוצג בדוגמאות. קודי השגיאות משתלבים יפה עם פונקציות, מה שמאפשר ניהול שגיאות מודולרי וקריא.

## ראה גם
- תיעוד Fish על תנאים: https://fishshell.com/docs/current/language.html#conditionals
- הדרכת Fish על טיפול בשגיאות: https://fishshell.com/docs/current/tutorial.html#error-handling
