---
aliases:
- /he/c/sending-an-http-request/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:09:32.339137-07:00
description: "\u05E9\u05DC\u05D9\u05D7\u05EA \u05D1\u05E7\u05E9\u05EA HTTP \u05DB\u05D5\
  \u05DC\u05DC\u05EA \u05D9\u05E6\u05D9\u05E8\u05D4 \u05D5\u05E9\u05D9\u05D2\u05D5\
  \u05E8 \u05E9\u05DC \u05D1\u05E7\u05E9\u05D4 \u05DC\u05E9\u05E8\u05EA \u05D0\u05D9\
  \u05E0\u05D8\u05E8\u05E0\u05D8 \u05DB\u05D3\u05D9 \u05DC\u05D0\u05D7\u05D6\u05E8\
  \ \u05D0\u05D5 \u05DC\u05E9\u05DC\u05D5\u05D7 \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD\
  . \u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\
  \u05EA \u05D1-C \u05DB\u05D3\u05D9 \u05DC\u05EA\u05E7\u05E9\u05E8 \u05E2\u05DD \u05DE\
  \u05DE\u05E9\u05E7\u05D9 API \u05E9\u05DC \u05D0\u05D9\u05E0\u05D8\u05E8\u05E0\u05D8\
  , \u05DC\u05D4\u05D5\u05E8\u05D9\u05D3 \u05D3\u05E4\u05D9\u2026"
lastmod: 2024-02-18 23:08:53.338413
model: gpt-4-0125-preview
summary: "\u05E9\u05DC\u05D9\u05D7\u05EA \u05D1\u05E7\u05E9\u05EA HTTP \u05DB\u05D5\
  \u05DC\u05DC\u05EA \u05D9\u05E6\u05D9\u05E8\u05D4 \u05D5\u05E9\u05D9\u05D2\u05D5\
  \u05E8 \u05E9\u05DC \u05D1\u05E7\u05E9\u05D4 \u05DC\u05E9\u05E8\u05EA \u05D0\u05D9\
  \u05E0\u05D8\u05E8\u05E0\u05D8 \u05DB\u05D3\u05D9 \u05DC\u05D0\u05D7\u05D6\u05E8\
  \ \u05D0\u05D5 \u05DC\u05E9\u05DC\u05D5\u05D7 \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD\
  . \u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\
  \u05EA \u05D1-C \u05DB\u05D3\u05D9 \u05DC\u05EA\u05E7\u05E9\u05E8 \u05E2\u05DD \u05DE\
  \u05DE\u05E9\u05E7\u05D9 API \u05E9\u05DC \u05D0\u05D9\u05E0\u05D8\u05E8\u05E0\u05D8\
  , \u05DC\u05D4\u05D5\u05E8\u05D9\u05D3 \u05D3\u05E4\u05D9\u2026"
title: "\u05E9\u05DC\u05D9\u05D7\u05EA \u05D1\u05E7\u05E9\u05EA HTTP"
---

{{< edit_this_page >}}

## מה ולמה?

שליחת בקשת HTTP כוללת יצירה ושיגור של בקשה לשרת אינטרנט כדי לאחזר או לשלוח נתונים. תכנתים עושים זאת ב-C כדי לתקשר עם ממשקי API של אינטרנט, להוריד דפי אינטרנט, או לתקשר ישירות מתוך היישומים שלהם עם שירותים מרושתים אחרים.

## איך לעשות:

כדי לשלוח בקשת HTTP ב-C, בדרך כלל תתבססו על ספריות כמו libcurl, מאחר שב-C אין תמיכה מובנית לפרוטוקולי אינטרנט. הנה דוגמה פשוטה בשימוש ב-libcurl לביצוע בקשת GET:

ראשית, ודאו ש-libcurl מותקן במערכת שלכם. לאחר מכן, כללו את הכותרות הנדרשות וקישרו כנגד ספריית libcurl בקובץ המקור שלכם:

```c
#include <stdio.h>
#include <curl/curl.h>

int main(void) {
    CURL *curl;
    CURLcode res;

    curl = curl_easy_init(); // אתחול ידית libcurl
    if(curl) {
        // הגדרת ה-URL שמקבל הידית libcurl
        curl_easy_setopt(curl, CURLOPT_URL, "http://example.com");
        // הגדרת פונקצית קולבק לקבלת הנתונים
        curl_easy_setopt(curl, CURLOPT_WRITEFUNCTION, NULL); 
        
        // ביצוע הבקשה, res יקבל את קוד החזרה
        res = curl_easy_perform(curl);
        // בדיקת שגיאות
        if(res != CURLE_OK)
            fprintf(stderr, "curl_easy_perform() failed: %s\n",
                    curl_easy_strerror(res));

        // ניקוי תמידי
        curl_easy_cleanup(curl);
    }
    return 0;
}
```

הדוגמה זו יכולה להיתרגם באמצעות שורת הפקודה `gcc -o http_request http_request.c -lcurl`, הרצתה אמורה לבצע בקשת GET פשוטה ל-"http://example.com".

### פלט דוגמה

מכיוון שהדוגמה לא מעבדת את תגובת השרת, הרצתה לא תייצר פלט גלוי מעבר להודעות שגיאה פוטנציאליות. השלבה של פונקציית קולבק לעיבוד נתונים שהתקבלו היא חיונית לאינטרקציה משמעותית.

## צלילה עמוקה

הרעיון של שליחת בקשות HTTP מתוך תוכנית C מבוסס על יכולות הרשת החזקות של השפה, יחד עם שימוש בספריות חיצוניות, מכיוון ש-C עצמה היא שפה ברמה נמוכה ללא תמיכה מובנית בפרוטוקולי אינטרנט ברמה גבוהה. בעבר, תכנתים היו משתמשים בצורה ידנית בתכנות socket ב-C, תהליך מורכב ומעייף, כדי לתקשר עם שרתי אינטרנט לפני בואם של ספריות מוקדשות כמו libcurl.

Libcurl, שנבנית על גבי C, מפשטת את התהליך, מוסיפה שכבת הפשטה מעל פרטי תכנות ה-socket והפרטים הספציפיים של הפרוטוקול HTTP. היא תומכת במגוון פרוטוקולים מעבר ל-HTTP/HTTPS, כולל FTP, SMTP, ועוד, והופכת אותה לכלי גמיש לתכנות רשת ב-C.

בעוד שהשימוש ב-libcurl לבקשות HTTP ב-C הוא פרקטי, התכנות המודרני לעיתים קרובות מתמקד בשפות עם תמיכה מובנית למשימות כאלו, כמו Python (ספריית requests) או JavaScript (API של Fetch). האלטרנטיבות הללו מציעות תחביר פשוט וקריא יותר על חשבון השליטה המדויקת והאפשרויות לאופטימיזציה של הביצועים האפשריות ב-C דרך ניהול ישיר של סוקטים ושימוש מדויק בספריות.

ליישומים קריטיים מבחינת ביצועים או כאשר נדרשת התקשרות ישירה ברמת המערכת, C נשארת אופציה נגישה, במיוחד עם libcurl שמפשטת את המורכבויות של תקשורת אינטרנט. עם זאת, לרוב האינטרקציות ברמה הגבוהה באינטרנט, בדיקת שפות תכנות מוקדשות לאינטרנט עשויה להוכיח אפקטיביות רבה יותר.
