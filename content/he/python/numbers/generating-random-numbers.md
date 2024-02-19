---
aliases:
- /he/python/generating-random-numbers/
date: 2024-01-27 20:35:54.231277-07:00
description: "\u05D9\u05E6\u05D9\u05E8\u05EA \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD\
  \ \u05D0\u05E7\u05E8\u05D0\u05D9\u05D9\u05DD \u05DB\u05D5\u05DC\u05DC\u05EA \u05D0\
  \u05EA \u05D9\u05E6\u05D9\u05E8\u05EA \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD \u05E9\
  \u05DC\u05D0 \u05E0\u05D9\u05EA\u05DF \u05DC\u05D7\u05D6\u05D5\u05EA \u05D0\u05D5\
  \u05EA\u05DD \u05D1\u05E6\u05D5\u05E8\u05D4 \u05E8\u05D0\u05D5\u05D9\u05D4 \u05D9\
  \u05D5\u05EA\u05E8 \u05DE\u05DE\u05E7\u05E8\u05D9\u05D5\u05EA, \u05DE\u05D4 \u05E9\
  \u05D7\u05E9\u05D5\u05D1 \u05DC\u05E4\u05D9\u05EA\u05D5\u05D7 \u05E1\u05D9\u05DE\
  \u05D5\u05DC\u05E6\u05D9\u05D5\u05EA, \u05DE\u05E9\u05D7\u05E7\u05D9\u05DD \u05D5\
  \u05D0\u05DC\u05D2\u05D5\u05E8\u05D9\u05EA\u05DE\u05D9\u05DD \u05D0\u05D1\u05D8\u05D7\
  \u05EA\u05D9\u05D9\u05DD. \u05EA\u05DB\u05E0\u05EA\u05D9\u05DD\u2026"
lastmod: 2024-02-18 23:08:52.432406
model: gpt-4-0125-preview
summary: "\u05D9\u05E6\u05D9\u05E8\u05EA \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD \u05D0\
  \u05E7\u05E8\u05D0\u05D9\u05D9\u05DD \u05DB\u05D5\u05DC\u05DC\u05EA \u05D0\u05EA\
  \ \u05D9\u05E6\u05D9\u05E8\u05EA \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD \u05E9\u05DC\
  \u05D0 \u05E0\u05D9\u05EA\u05DF \u05DC\u05D7\u05D6\u05D5\u05EA \u05D0\u05D5\u05EA\
  \u05DD \u05D1\u05E6\u05D5\u05E8\u05D4 \u05E8\u05D0\u05D5\u05D9\u05D4 \u05D9\u05D5\
  \u05EA\u05E8 \u05DE\u05DE\u05E7\u05E8\u05D9\u05D5\u05EA, \u05DE\u05D4 \u05E9\u05D7\
  \u05E9\u05D5\u05D1 \u05DC\u05E4\u05D9\u05EA\u05D5\u05D7 \u05E1\u05D9\u05DE\u05D5\
  \u05DC\u05E6\u05D9\u05D5\u05EA, \u05DE\u05E9\u05D7\u05E7\u05D9\u05DD \u05D5\u05D0\
  \u05DC\u05D2\u05D5\u05E8\u05D9\u05EA\u05DE\u05D9\u05DD \u05D0\u05D1\u05D8\u05D7\u05EA\
  \u05D9\u05D9\u05DD. \u05EA\u05DB\u05E0\u05EA\u05D9\u05DD\u2026"
title: "\u05D2\u05D9\u05DC\u05D5\u05D9 \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD \u05D0\
  \u05E7\u05E8\u05D0\u05D9\u05D9\u05DD"
---

{{< edit_this_page >}}

## מה ולמה?

יצירת מספרים אקראיים כוללת את יצירת מספרים שלא ניתן לחזות אותם בצורה ראויה יותר ממקריות, מה שחשוב לפיתוח סימולציות, משחקים ואלגוריתמים אבטחתיים. תכנתים עושים זאת כדי להכניס בלתי צפויות או לחקות תופעות מהעולם האמיתי באפליקציות שלהם.

## איך לעשות:

פייתון מספקת את המודול `random` שעוזר ביצירת מספרים אקראיים לשימושים שונים. הנה איך להתחיל:

1. **ייבוא המודול**
    ```Python
    import random
    ```

2. **יצירת מספר שלם אקראי**
    בין שני מספרים כלשהם.
    ```Python
    random_integer = random.randint(1, 10)
    print(random_integer)
    ```
    פלט לדוגמא: `7`

3. **יצירת מספר ממשי**
    בין 0 ל-1.
    ```Python
    random_float = random.random()
    print(random_float)
    ```
    פלט לדוגמא: `0.436432634653`

    אם צריך מספר ממשי בטווח אחר, להכפיל:
    ```Python
    random_float_range = random.random() * 5  # מ-0 עד 5
    print(random_float_range)
    ```
    פלט לדוגמא: `3.182093745`

4. **בחירת אלמנט אקראי מתוך רשימה**
    ```Python
    greetings = ['Hello', 'Hi', 'Hey', 'Hola', 'Bonjour']
    print(random.choice(greetings))
    ```
    פלט לדוגמא: `Hola`

5. **ערבוב רשימה**
    מושלם למשחקי קלפים או כל אפליקציה שמצריכה ערבוב של הסדר.
    ```Python
    numbers = list(range(10))
    random.shuffle(numbers)
    print(numbers)
    ```
    פלט לדוגמא: `[2, 5, 0, 4, 9, 8, 1, 7, 6, 3]`

## לעומק

המודול `random` בפייתון משתמש במחולל מספרים פסאודו-אקראיים (PRNG), בפרט אלגוריתם Mersenne Twister, שמתאים לשימושים כלליים אך לא מתאים למטרות קריפטוגרפיות עקב הניתנות שלו לחיזוי אם מתבוננים במספיק פלטים. המודול `secrets`, שהוצג בפייתון 3.6, מציע חלופה טובה יותר ליצירת מספרים אקראיים חזקים מבחינה קריפטוגרפית, שימושי במיוחד באפליקציות רגישות לאבטחה. לדוגמה, יצירת טוקן אקראי ובטוח לקישור איפוס סיסמה:

```Python
import secrets
token = secrets.token_hex(16)
print(token)
```

בהיסטוריה, יצירת מספרים אקראיים שהם באמת אקראיים הייתה אתגר במחשוב, עם שיטות מוקדמות המתבססות על תופעות פיזיות או הזנות ידנית של זרעים. הפיתוח והאימוץ של אלגוריתמים כמו Mersenne Twister (שנמצא בשימוש כברירת מחדל במודול `random` של פייתון לפחות עד לעדכון הידע האחרון שלי ב-2023) סימן התקדמות נכבדת. עם זאת, החיפוש המתמשך אחר אלגוריתמים יותר בטוחים ויעילים הביא לכלול את המודול `secrets` למשימות הקשורות לקריפטוגרפיה. התפתחות זו משקפת את הגדלת החשיבות של האבטחה בפיתוח תוכנה ואת הצורך באקראיות חזקה יותר באפליקציות החל מהצפנה ועד יצירת טוקנים בטוחים.
