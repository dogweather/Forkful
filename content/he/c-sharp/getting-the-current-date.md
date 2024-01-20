---
title:                "קבלת התאריך הנוכחי"
html_title:           "C#: קבלת התאריך הנוכחי"
simple_title:         "קבלת התאריך הנוכחי"
programming_language: "C#"
category:             "C#"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/c-sharp/getting-the-current-date.md"
---

{{< edit_this_page >}}

## מה ולמה?
בתיכנות, קבלת התאריך הנוכחי היא פעולה שמאפשרת לנו לקבל את התאריך והשעה בימים, שעות, דקות, ושניות של המערכת. תכנתים משתמשים בפונקציונאליות הזו כדי לאכוף תוקף לנתונים, לארגן איבנטים בהתאם לזמן, ועוד.

## איך לעשות:
הי מתכנתים, בואו ניכנס לעניין. לקבלת התאריך הנוכחי ב-C#, משתמשים בפונקציה `DateTime.Now`. קוד פשוט שמדגים את השימוש בפונקציה הזו:

```C#
using System;

public class Program
{
    public static void Main()
    {
        DateTime currentDateTime = DateTime.Now;
        Console.WriteLine("התאריך והשעה הנוכחיים הם: " + currentDateTime);
    }
}
```

הפלט מעל יהיה:
```C#
התאריך והשעה הנוכחיים הם: 2022-07-08 13:40:00
```

לפלט הזה יהיו תאריך ושעה שונים, בהתאמה לזמן ברגע ההרצה.

## מבט עמוק
המחלקה `DateTime` אכן מועילה מאוד, אך היא לא הייתה חלק מהשפה מההתחלה. שיפורים בשפה וב.Net Framework עזרו לפתח את היכולות הזו.

ישנן חלופות לפונקציה `DateTime.Now`. למשל, `DateTime.UtcNow` נותן לך את התאריך והשעה הנוכחיים לפי הזמן הים-תיכוני המתואם (UTC).

אגב, הפונקציה `DateTime.Now` מחזירה את התאריך והשעה לפי הזמן המקומי של המערכת, כך שאם שניות הקפיצה ושניות השחזור הן בעייתיות או אם התאריך והשעה שונים באופן עצמאי, זמן UTC יעשה את העבודה.

## ראו גם
ביקור בקישורים הבאים יספק לך מידע נרחב יותר:
1. [מסמך Microsoft: ייחוס זמן ב-C#](https://docs.microsoft.com/he-il/dotnet/csharp/programming-guide/concepts/datetime)
2. [ראיון עם מפתחים של C# על DateTime](https://youtu.be/N_fb4-BHNWc)
3. [השוואה בין DateTime ו-TimeSpan ב-C#](https://www.c-sharpcorner.com/article/difference-between-datetime-and-timespan-in-chash/)