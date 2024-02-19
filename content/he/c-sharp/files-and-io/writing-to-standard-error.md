---
aliases:
- /he/c-sharp/writing-to-standard-error/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:33:23.270072-07:00
description: "\u05DB\u05EA\u05D9\u05D1\u05D4 \u05DC\u05E9\u05D2\u05D9\u05D0\u05D4\
  \ \u05E1\u05D8\u05E0\u05D3\u05E8\u05D8\u05D9\u05EA (stderr) \u05D1-C# \u05DB\u05D5\
  \u05DC\u05DC\u05EA \u05D4\u05DB\u05D5\u05D5\u05E0\u05EA \u05D4\u05D5\u05D3\u05E2\
  \u05D5\u05EA \u05E9\u05D2\u05D9\u05D0\u05D4 \u05D5\u05D0\u05D1\u05D7\u05D5\u05DF\
  \ \u05D1\u05E0\u05E4\u05E8\u05D3 \u05DE\u05D4\u05E4\u05DC\u05D8 \u05D4\u05E8\u05D2\
  \u05D9\u05DC (stdout), \u05DB\u05D3\u05D9 \u05DC\u05E2\u05D6\u05D5\u05E8 \u05DC\u05DE\
  \u05E9\u05EA\u05DE\u05E9\u05D9\u05DD \u05D5\u05DC\u05DE\u05E4\u05EA\u05D7\u05D9\u05DD\
  \ \u05DC\u05D4\u05D1\u05D3\u05D9\u05DC \u05D1\u05D9\u05DF \u05E4\u05DC\u05D8 \u05D4\
  \u05EA\u05D5\u05DB\u05E0\u05D9\u05EA \u05D4\u05E8\u05D2\u05D9\u05DC\u2026"
lastmod: 2024-02-18 23:08:52.859362
model: gpt-4-0125-preview
summary: "\u05DB\u05EA\u05D9\u05D1\u05D4 \u05DC\u05E9\u05D2\u05D9\u05D0\u05D4 \u05E1\
  \u05D8\u05E0\u05D3\u05E8\u05D8\u05D9\u05EA (stderr) \u05D1-C# \u05DB\u05D5\u05DC\
  \u05DC\u05EA \u05D4\u05DB\u05D5\u05D5\u05E0\u05EA \u05D4\u05D5\u05D3\u05E2\u05D5\
  \u05EA \u05E9\u05D2\u05D9\u05D0\u05D4 \u05D5\u05D0\u05D1\u05D7\u05D5\u05DF \u05D1\
  \u05E0\u05E4\u05E8\u05D3 \u05DE\u05D4\u05E4\u05DC\u05D8 \u05D4\u05E8\u05D2\u05D9\
  \u05DC (stdout), \u05DB\u05D3\u05D9 \u05DC\u05E2\u05D6\u05D5\u05E8 \u05DC\u05DE\u05E9\
  \u05EA\u05DE\u05E9\u05D9\u05DD \u05D5\u05DC\u05DE\u05E4\u05EA\u05D7\u05D9\u05DD\
  \ \u05DC\u05D4\u05D1\u05D3\u05D9\u05DC \u05D1\u05D9\u05DF \u05E4\u05DC\u05D8 \u05D4\
  \u05EA\u05D5\u05DB\u05E0\u05D9\u05EA \u05D4\u05E8\u05D2\u05D9\u05DC\u2026"
title: "\u05DB\u05EA\u05D9\u05D1\u05D4 \u05DC\u05E9\u05D2\u05D9\u05D0\u05D4 \u05D4\
  \u05EA\u05E7\u05E0\u05D9\u05EA"
---

{{< edit_this_page >}}

## מה ולמה?
כתיבה לשגיאה סטנדרטית (stderr) ב-C# כוללת הכוונת הודעות שגיאה ואבחון בנפרד מהפלט הרגיל (stdout), כדי לעזור למשתמשים ולמפתחים להבדיל בין פלט התוכנית הרגיל להתראות שגיאה. מתכנתים עושים זאת כדי להפוך את הניפוי שגיאות והתיעוד ליעילים יותר, מה שמאפשר פעולה חלקה יותר ותחזוקה של יישומים.

## איך לעשות:
ב-C#, ניתן לכתוב לשגיאה סטנדרטית באמצעות זרם ה`Console.Error`. זרם זה משמש במיוחד עבור הודעות שגיאה ואבחון. הנה דוגמה בסיסית:

```csharp
Console.Error.WriteLine("Error: Failed to process the request.");
```

דוגמת פלט (ל-stderr):
```
Error: Failed to process the request.
```

לסצנריות שבהן אתם עשויים להשתמש בספרייה צד שלישי שמציעה יכולות תיעוד מתקדמות, כמו `Serilog` או `NLog`, תוכלו להגדיר את הספריות הללו לכתוב יומני שגיאות ל-stderr. למרות שהדוגמאות הללו מתמקדות בהפניית קונסול פשוטה, זכרו שביישומים ייצוריים, מסגרות תיעוד מציעות אפשרויות טיפול בשגיאות ופלט יותר חזקות. הנה דוגמה פשוטה עם `Serilog`:

ראשית, התקינו את החבילה של Serilog ואת הברז שלה לקונסול:

```
Install-Package Serilog
Install-Package Serilog.Sinks.Console
```

לאחר מכן, הגדירו את Serilog לכתוב ל-stderr:

```csharp
using Serilog;

Log.Logger = new LoggerConfiguration()
    .WriteTo.Console(standardErrorFromLevel: Serilog.Events.LogEventLevel.Error)
    .CreateLogger();

Log.Information("This is a normal message.");
Log.Error("This is an error message.");
```

דוגמת פלט (ל-stderr עבור הודעת השגיאה):
```
[15:04:20 ERR] This is an error message.
```

הערה: ההגדרה `standardErrorFromLevel` בברז הקונסול של Serilog מפנה את כל אירועי התיעוד ברמת הקובעת המצוינת (שגיאה, במקרה זה) או גבוהה יותר לזרם השגיאה הסטנדרטית, בעוד שהודעות ברמות נמוכות יותר כמו מידע נכתבות לזרם הפלט הסטנדרטי.
