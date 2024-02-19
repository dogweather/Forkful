---
aliases:
- /he/python/handling-errors/
date: 2024-01-26 00:56:43.028870-07:00
description: "\u05D8\u05D9\u05E4\u05D5\u05DC \u05D1\u05E9\u05D2\u05D9\u05D0\u05D5\u05EA\
  \ \u05D1\u05E4\u05D9\u05D9\u05EA\u05D5\u05DF (\u05D0\u05D5 \u05D1\u05DB\u05DC \u05E9\
  \u05E4\u05EA \u05EA\u05DB\u05E0\u05D5\u05EA) \u05DE\u05D3\u05D5\u05D1\u05E8 \u05D1\
  \u05E6\u05D9\u05E4\u05D9\u05D9\u05D4 \u05DC\u05D1\u05DC\u05EA\u05D9 \u05E6\u05E4\
  \u05D5\u05D9 \u2013 \u05D6\u05D5 \u05D0\u05DE\u05E0\u05D5\u05EA \u05E9\u05DC \u05E0\
  \u05D9\u05D4\u05D5\u05DC \u05D7\u05E1\u05D9\u05DF \u05DB\u05D0\u05E9\u05E8 \u05D3\
  \u05D1\u05E8\u05D9\u05DD \u05D4\u05D5\u05DC\u05DB\u05D9\u05DD \u05D3\u05E8\u05D5\
  \u05DE\u05D4 \u05D1\u05E7\u05D5\u05D3 \u05E9\u05DC\u05DA. \u05D0\u05E0\u05D5 \u05E2\
  \u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9 \u05DC\u05DE\u05E0\
  \u05D5\u05E2\u2026"
lastmod: 2024-02-18 23:08:52.444399
model: gpt-4-1106-preview
summary: "\u05D8\u05D9\u05E4\u05D5\u05DC \u05D1\u05E9\u05D2\u05D9\u05D0\u05D5\u05EA\
  \ \u05D1\u05E4\u05D9\u05D9\u05EA\u05D5\u05DF (\u05D0\u05D5 \u05D1\u05DB\u05DC \u05E9\
  \u05E4\u05EA \u05EA\u05DB\u05E0\u05D5\u05EA) \u05DE\u05D3\u05D5\u05D1\u05E8 \u05D1\
  \u05E6\u05D9\u05E4\u05D9\u05D9\u05D4 \u05DC\u05D1\u05DC\u05EA\u05D9 \u05E6\u05E4\
  \u05D5\u05D9 \u2013 \u05D6\u05D5 \u05D0\u05DE\u05E0\u05D5\u05EA \u05E9\u05DC \u05E0\
  \u05D9\u05D4\u05D5\u05DC \u05D7\u05E1\u05D9\u05DF \u05DB\u05D0\u05E9\u05E8 \u05D3\
  \u05D1\u05E8\u05D9\u05DD \u05D4\u05D5\u05DC\u05DB\u05D9\u05DD \u05D3\u05E8\u05D5\
  \u05DE\u05D4 \u05D1\u05E7\u05D5\u05D3 \u05E9\u05DC\u05DA. \u05D0\u05E0\u05D5 \u05E2\
  \u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9 \u05DC\u05DE\u05E0\
  \u05D5\u05E2\u2026"
title: "\u05D8\u05D9\u05E4\u05D5\u05DC \u05D1\u05E9\u05D2\u05D9\u05D0\u05D5\u05EA"
---

{{< edit_this_page >}}

## מה ולמה?

טיפול בשגיאות בפייתון (או בכל שפת תכנות) מדובר בציפייה לבלתי צפוי – זו אמנות של ניהול חסין כאשר דברים הולכים דרומה בקוד שלך. אנו עושים זאת כדי למנוע קריסות, להדריך משתמשים, ולעשות את התכניות שלנו חזקות ואמינות.

## איך לעשות:

``` Python
# בלוק try-except בסיסי
try:
    # קוד מסוכן
    number = int(input("הכנס מספר: "))
except ValueError:
    # טיפול בשגיאה
    print("זה לא מספר!")

# ציון מספר חריגות
try:
    # קוד שעלול להעלות חריגות שונות
    result = 10 / int(input("הכנס מחלק: "))
except ZeroDivisionError:
    print("אופס! אי אפשר לחלק באפס.")
except ValueError:
    print("אני צריך מספר, חבר.")

# שימוש ב-else ו-finally
try:
    number = int(input("הכנס מספר לריבוע: "))
except ValueError:
    print("אמרתי מספר!")
else:
    # לא התרחשו שגיאות
    print("המספר שלך בריבוע הוא:", number**2)
finally:
    # תמיד מתבצע
    print("תודה שניסית את זה!")
```

דוגמת פלט כאשר מזינים מספר לא חוקי עבור הבלוק הראשון:
```
הכנס מספר: שלום
זה לא מספר!
```

## צלילה עמוקה

מאז שעלתה התכנות, טיפול בשגיאות הייתה חיונית. השיטות הראשוניות היו פרימיטיביות, כמו בדיקת תנאים לפני כל פעולה מסוכנת. תחביר ה-`try-except` של פייתון בא ממורשת של טיפול בחריגות בשפות ישנות יותר כמו C++ וג'אווה, מפשט את התהליך.

כאשר אתה `try` בלוק של קוד, פייתון מחפש כל חריגות. אם שגיאה צצה, הבלוק `except` תופס אותה. אפשר להיות ספציפיים לגבי החריגות שתופסים או לתפוס את כולם עם `except` ריק. עם זאת, ספציפיות תחילה היא הגישה הטובה יותר – היא מדויקת, לא רשת תפיסה לכל.

`else` ו-`finally` הם תוספות למושג זה. הבלוק `else` רץ אם הבלוק try חופשי משגיאות. `finally` הוא חבר אמין שרץ ללא תלות במה – חשבו על פעולות ניקוי.

אלטרנטיבות? ברור שיש. כמה שפות משתמשות בקודי חזרה במקום בחריגות. ייתכן שתיתקל גם בהצהרות `with` עבור טיפול במשאבים או ב`אסרציות` שבודקות תנאים במהלך פיתוח. אבל כאשר אנחנו מדברים על אסטרטגיות טיפול בשגיאות אמינות, הדגם של try-catch יוצא דופן בבירור ומבנה שלו.

## ראה גם

הנה כמה מקורות נוספים טובים להעמקה עוד יותר:

- התיעוד הרשמי של פייתון על שגיאות וחריגות: [תיעוד פייתון – שגיאות וחריגות](https://docs.python.org/3/tutorial/errors.html)
- המדריך של Real Python לנושא: [Real Python - בלוק try/except/else/finally](https://realpython.com/python-exceptions/)
- דיון מושכל על מיטב הליכים לטיפול בשגיאות: [Stack Overflow – איך להתעלם באופן נכון מחריגות?](https://stackoverflow.com/questions/4990718/about-catching-any-exception)
