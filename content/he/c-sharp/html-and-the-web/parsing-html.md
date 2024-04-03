---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:12:16.458692-07:00
description: "\u05E0\u05D9\u05EA\u05D5\u05D7 HTML \u05D1\u05EA\u05DB\u05E0\u05D5\u05EA\
  \ \u05DB\u05D5\u05DC\u05DC \u05D0\u05EA \u05D4\u05E0\u05D9\u05EA\u05D5\u05D7 \u05E9\
  \u05DC \u05DE\u05D1\u05E0\u05D4 \u05DE\u05E1\u05DE\u05DA HTML, \u05DE\u05D4 \u05E9\
  \u05DE\u05D0\u05E4\u05E9\u05E8 \u05DC\u05DA \u05DC\u05D7\u05DC\u05E5, \u05DC\u05E9\
  \u05E0\u05D5\u05EA \u05D5\u05DC\u05D4\u05EA\u05E2\u05E8\u05D1 \u05D1\u05EA\u05D5\
  \u05DB\u05E0\u05D9\u05D5 \u05D1\u05D0\u05D5\u05E4\u05DF \u05EA\u05D5\u05DB\u05E0\
  \u05D9\u05EA\u05D9. \u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05E2\u05D5\u05E9\
  \u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9 \u05DC\u05D0\u05D5\u05D8\u05DE\
  \u05D8 \u05D2\u05D9\u05E8\u05D9\u05D3\u05EA \u05D0\u05EA\u05E8\u05D9\u05DD,\u2026"
lastmod: '2024-03-13T22:44:39.339088-06:00'
model: gpt-4-0125-preview
summary: "\u05E0\u05D9\u05EA\u05D5\u05D7 HTML \u05D1\u05EA\u05DB\u05E0\u05D5\u05EA\
  \ \u05DB\u05D5\u05DC\u05DC \u05D0\u05EA \u05D4\u05E0\u05D9\u05EA\u05D5\u05D7 \u05E9\
  \u05DC \u05DE\u05D1\u05E0\u05D4 \u05DE\u05E1\u05DE\u05DA HTML, \u05DE\u05D4 \u05E9\
  \u05DE\u05D0\u05E4\u05E9\u05E8 \u05DC\u05DA \u05DC\u05D7\u05DC\u05E5, \u05DC\u05E9\
  \u05E0\u05D5\u05EA \u05D5\u05DC\u05D4\u05EA\u05E2\u05E8\u05D1 \u05D1\u05EA\u05D5\
  \u05DB\u05E0\u05D9\u05D5 \u05D1\u05D0\u05D5\u05E4\u05DF \u05EA\u05D5\u05DB\u05E0\
  \u05D9\u05EA\u05D9."
title: "\u05E4\u05D9\u05E2\u05E0\u05D5\u05D7 HTML"
weight: 43
---

## איך לעשות:
למרות ש-NET מספקת תמיכה בסיסית בעבודה עם HTML, כמו למשל `HttpClient` לשליפת דפי אינטרנט, חסרה בה גרזנת HTML מובנית ומקיפה. לכן, רוב מפתחי C# מפנים פניה לספריות צד שלישי פופולריות כמו HtmlAgilityPack או AngleSharp ליכולת ניתוח HTML עמידה. שתי הספריות מאפשרות שאילתות, שינוי ועיבור קל של DOM ה-HTML.

### שימוש ב-HtmlAgilityPack
1. **התקנת HtmlAgilityPack**: ראשית, הוסף את החבילה של HtmlAgilityPack לפרויקט שלך דרך NuGet.
   ```
   Install-Package HtmlAgilityPack
   ```

2. **דוגמת קוד**: לנתח מחרוזת HTML, ולחלץ את הכותרות של כל אלמנטי `<h1>`.

   ```csharp
   using HtmlAgilityPack;
   using System;
   using System.Linq;

   class Program
   {
       static void Main(string[] args)
       {
           var html = @"<html>
                         <body>
                             <h1>Title 1</h1>
                             <h1>Title 2</h1>
                         </body>
                        </html>";
           var htmlDoc = new HtmlDocument();
           htmlDoc.LoadHtml(html);

           var h1Tags = htmlDoc.DocumentNode.SelectNodes("//h1").Select(node => node.InnerText);
           foreach (var title in h1Tags)
           {
               Console.WriteLine(title);
           }
       }
   }
   ```

   **פלט לדוגמא:**
   ```
   Title 1
   Title 2
   ```

### שימוש ב-AngleSharp
1. **התקנת AngleSharp**: הוסף את ספריית AngleSharp לפרויקט שלך דרך NuGet.
   ```
   Install-Package AngleSharp
   ```

2. **דוגמת קוד**: טעינת מסמך HTML ושאילתא של אלמנטי `div` עם מחלקה ספציפית.

   ```csharp
   using AngleSharp;
   using AngleSharp.Dom;
   using System;
   using System.Linq;
   using System.Threading.Tasks;

   class Program
   {
       static async Task Main(string[] args)
       {
           var context = BrowsingContext.New(Configuration.Default);
           var document = await context.OpenAsync(req => req.Content("<div class='item'>Item 1</div><div class='item'>Item 2</div>"));

           var items = document.QuerySelectorAll(".item").Select(element => element.TextContent);
           foreach (var item in items)
           {
               Console.WriteLine(item);
           }
       }
   }
   ```

   **פלט לדוגמא:**
   ```
   Item 1
   Item 2
   ```

HtmlAgilityPack ו-AngleSharp הם כלים עוצמתיים לניתוח HTML, אך הבחירה ביניהם עשויה להיות תלויה בדרישות הפרויקט הספציפיות, שיקולי ביצועים, או העדפה אישית בעיצוב ה-API.
