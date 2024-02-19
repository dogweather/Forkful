---
aliases:
- /he/java/comparing-two-dates/
date: 2024-01-20 17:33:18.398856-07:00
description: "\u05DB\u05E9\u05D0\u05E0\u05D7\u05E0\u05D5 \u05DE\u05E9\u05D5\u05D5\u05D9\
  \u05DD \u05E9\u05EA\u05D9 \u05EA\u05D0\u05E8\u05D9\u05DB\u05D9\u05DD, \u05D0\u05E0\
  \u05D7\u05E0\u05D5 \u05D1\u05E2\u05E6\u05DD \u05D1\u05D5\u05D3\u05E7\u05D9\u05DD\
  \ \u05D0\u05D9\u05D6\u05D4 \u05EA\u05D0\u05E8\u05D9\u05DA \u05E7\u05E8\u05D4 \u05DC\
  \u05E4\u05E0\u05D9 \u05D4\u05E9\u05E0\u05D9, \u05D0\u05D5 \u05D0\u05DD \u05D4\u05DD\
  \ \u05D0\u05D5\u05EA\u05D5 \u05D4\u05D9\u05D5\u05DD. \u05D6\u05D4 \u05D7\u05E9\u05D5\
  \u05D1 \u05D1\u05EA\u05D7\u05D5\u05DD \u05DB\u05DE\u05D5 \u05DC\u05D5\u05D2\u05D9\
  \u05E1\u05D8\u05D9\u05E7\u05D4, \u05E0\u05D9\u05D4\u05D5\u05DC \u05D0\u05D9\u05E8\
  \u05D5\u05E2\u05D9\u05DD, \u05D5\u05DB\u05DC \u05DE\u05E7\u05D5\u05DD \u05E9\u05D1\
  \u05D5 \u05E1\u05D9\u05D3\u05D5\u05E8\u2026"
lastmod: 2024-02-18 23:08:52.721974
model: gpt-4-1106-preview
summary: "\u05DB\u05E9\u05D0\u05E0\u05D7\u05E0\u05D5 \u05DE\u05E9\u05D5\u05D5\u05D9\
  \u05DD \u05E9\u05EA\u05D9 \u05EA\u05D0\u05E8\u05D9\u05DB\u05D9\u05DD, \u05D0\u05E0\
  \u05D7\u05E0\u05D5 \u05D1\u05E2\u05E6\u05DD \u05D1\u05D5\u05D3\u05E7\u05D9\u05DD\
  \ \u05D0\u05D9\u05D6\u05D4 \u05EA\u05D0\u05E8\u05D9\u05DA \u05E7\u05E8\u05D4 \u05DC\
  \u05E4\u05E0\u05D9 \u05D4\u05E9\u05E0\u05D9, \u05D0\u05D5 \u05D0\u05DD \u05D4\u05DD\
  \ \u05D0\u05D5\u05EA\u05D5 \u05D4\u05D9\u05D5\u05DD. \u05D6\u05D4 \u05D7\u05E9\u05D5\
  \u05D1 \u05D1\u05EA\u05D7\u05D5\u05DD \u05DB\u05DE\u05D5 \u05DC\u05D5\u05D2\u05D9\
  \u05E1\u05D8\u05D9\u05E7\u05D4, \u05E0\u05D9\u05D4\u05D5\u05DC \u05D0\u05D9\u05E8\
  \u05D5\u05E2\u05D9\u05DD, \u05D5\u05DB\u05DC \u05DE\u05E7\u05D5\u05DD \u05E9\u05D1\
  \u05D5 \u05E1\u05D9\u05D3\u05D5\u05E8\u2026"
title: "\u05D4\u05E9\u05D5\u05D5\u05D0\u05EA \u05E9\u05EA\u05D9 \u05EA\u05D0\u05E8\
  \u05D9\u05DB\u05D9\u05DD"
---

{{< edit_this_page >}}

## מה ולמה?
כשאנחנו משווים שתי תאריכים, אנחנו בעצם בודקים איזה תאריך קרה לפני השני, או אם הם אותו היום. זה חשוב בתחום כמו לוגיסטיקה, ניהול אירועים, וכל מקום שבו סידור הזמן קריטי להצלחה.

## איך לעשות:
בואו נראה כמה קוד Java שמשווים תאריכים תוך שימוש ב-java.time.LocalDate.
```java
import java.time.LocalDate;
import java.time.Period;

public class DatesComparison {
    public static void main(String[] args) {
        LocalDate date1 = LocalDate.of(2023, 5, 15);
        LocalDate date2 = LocalDate.now();

        // בדיקה איזה תאריך מוקדם יותר
        if (date1.isBefore(date2)) {
            System.out.println("date1 is before date2");
        } else if (date1.isAfter(date2)) {
            System.out.println("date1 is after date2");
        } else {
            System.out.println("date1 is equal to date2");
        }

        // חישוב ההפרש בין התאריכים
        Period period = Period.between(date1, date2);
        System.out.println("Years: " + period.getYears() + 
                           ", Months: " + period.getMonths() + 
                           ", Days: " + period.getDays());
    }
}
```
פלט משוער (תלוי בתאריך הנוכחי):
```plaintext
date1 is after date2
Years: 0, Months: 1, Days: 15
```

## ניתוח עמוק:
לפני Java 8, היינו משתמשים בjava.util.Date וjava.util.Calendar, אבל הם לא היו אינטואיטיביים וידידותיים. מאז Java 8, java.time.* (JSR-310) הם הפתרון המועדף, שנותן דרך נוחה ומדויקת לעבוד עם תאריכים וזמנים. תוספת הjava.time.LocalDate מיועדת לתאריך בלבד, ללא זמן או אזור זמן, שמועיל להשוואה פשוטה כמו בדוגמא למעלה.

אלטרנטיבות כוללות ספריות חיצוניות כמו Joda-Time, שימשה כהשראה לjava.time ועדיין משמשת בפרויקטים קודמים. עם התקדמות הזמן והדורות של ה-Java, התמיכה בפיצ’רים חדשים יותר ב-java.time הופכת אותה לאופציה המועדפת.

## ראה גם:
- [Java 8 LocalDate](https://docs.oracle.com/javase/8/docs/api/java/time/LocalDate.html) - מסמך ה-API הרשמי למחלקת LocalDate.
- [JSR 310: Date and Time API](https://www.jcp.org/en/jsr/detail?id=310) - התקן הרשמי של Java API לתאריכים וזמנים.
- [Joda-Time](https://www.joda.org/joda-time/) - ספריית ניהול תאריכים וזמנים.
