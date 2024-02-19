---
aliases:
- /he/c/sending-an-http-request-with-basic-authentication/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:10:05.825602-07:00
description: "\u05E9\u05DC\u05D9\u05D7\u05EA \u05D1\u05E7\u05E9\u05EA HTTP \u05E2\u05DD\
  \ \u05D0\u05D9\u05DE\u05D5\u05EA \u05D1\u05E1\u05D9\u05E1\u05D9 \u05D1-C \u05DB\u05D5\
  \u05DC\u05DC\u05EA \u05D9\u05E6\u05D9\u05E8\u05EA \u05D1\u05E7\u05E9\u05EA HTTP\
  \ \u05D4\u05DB\u05D5\u05DC\u05DC\u05EA \u05DB\u05D5\u05EA\u05E8\u05EA \u05D0\u05D9\
  \u05DE\u05D5\u05EA \u05E2\u05DD \u05E0\u05EA\u05D5\u05E0\u05D9 \u05D4\u05DE\u05E9\
  \u05EA\u05DE\u05E9 \u05DE\u05E7\u05D5\u05D3\u05D3\u05D9\u05DD \u05D1-Base64. \u05D6\
  \u05D5\u05D4\u05D9 \u05E9\u05D9\u05D8\u05D4 \u05E0\u05E4\u05D5\u05E6\u05D4 \u05DC\
  \u05D4\u05D5\u05E1\u05E4\u05EA \u05E9\u05DB\u05D1\u05EA \u05D0\u05D9\u05DE\u05D5\
  \u05EA \u05E4\u05E9\u05D5\u05D8\u05D4\u2026"
lastmod: 2024-02-18 23:08:53.341834
model: gpt-4-0125-preview
summary: "\u05E9\u05DC\u05D9\u05D7\u05EA \u05D1\u05E7\u05E9\u05EA HTTP \u05E2\u05DD\
  \ \u05D0\u05D9\u05DE\u05D5\u05EA \u05D1\u05E1\u05D9\u05E1\u05D9 \u05D1-C \u05DB\u05D5\
  \u05DC\u05DC\u05EA \u05D9\u05E6\u05D9\u05E8\u05EA \u05D1\u05E7\u05E9\u05EA HTTP\
  \ \u05D4\u05DB\u05D5\u05DC\u05DC\u05EA \u05DB\u05D5\u05EA\u05E8\u05EA \u05D0\u05D9\
  \u05DE\u05D5\u05EA \u05E2\u05DD \u05E0\u05EA\u05D5\u05E0\u05D9 \u05D4\u05DE\u05E9\
  \u05EA\u05DE\u05E9 \u05DE\u05E7\u05D5\u05D3\u05D3\u05D9\u05DD \u05D1-Base64. \u05D6\
  \u05D5\u05D4\u05D9 \u05E9\u05D9\u05D8\u05D4 \u05E0\u05E4\u05D5\u05E6\u05D4 \u05DC\
  \u05D4\u05D5\u05E1\u05E4\u05EA \u05E9\u05DB\u05D1\u05EA \u05D0\u05D9\u05DE\u05D5\
  \u05EA \u05E4\u05E9\u05D5\u05D8\u05D4\u2026"
title: "\u05E9\u05DC\u05D9\u05D7\u05EA \u05D1\u05E7\u05E9\u05EA HTTP \u05E2\u05DD\
  \ \u05D0\u05D9\u05DE\u05D5\u05EA \u05D1\u05E1\u05D9\u05E1\u05D9"
---

{{< edit_this_page >}}

## מה ולמה?
שליחת בקשת HTTP עם אימות בסיסי ב-C כוללת יצירת בקשת HTTP הכוללת כותרת אימות עם נתוני המשתמש מקודדים ב-Base64. זוהי שיטה נפוצה להוספת שכבת אימות פשוטה לבקשות HTTP, מאפשרת גישה מתוכנתת למשאבים מוגבלים.

## איך לעשות:
כדי לשלוח בקשת HTTP עם אימות בסיסי ב-C, נצטרך להשתמש בספריית libcurl, ספריית העברת URL צד לקוח פופולרית, גמישה וקלה לשימוש. היא מטפלת במגוון פרוטוקולים, כולל HTTP ו-HTTPS, מה שמקל על המשימה שלנו. הבטח ש-libcurl מותקנת במערכת שלך לפני שתמשיך. הנה דוגמה בסיסית שמדגימה איך לשלוח בקשת GET עם אימות בסיסי:

```c
#include <stdio.h>
#include <curl/curl.h>

int main(void) {
    CURL *curl;
    CURLcode res;

    curl_global_init(CURL_GLOBAL_DEFAULT);

    curl = curl_easy_init();
    if(curl) {
        // ה-URL אליו נשלחת הבקשה
        curl_easy_setopt(curl, CURLOPT_URL, "http://example.com/resource");
        // מאפשר שימוש באימות בסיסי
        curl_easy_setopt(curl, CURLOPT_HTTPAUTH, CURLAUTH_BASIC);
        // מספק שם משתמש וסיסמה לאימות הבסיסי
        curl_easy_setopt(curl, CURLOPT_USERPWD, "username:password");

        // ביצוע הבקשת GET
        res = curl_easy_perform(curl);

        // בדיקת שגיאות
        if(res != CURLE_OK)
            fprintf(stderr, "curl_easy_perform() failed: %s\n",
                    curl_easy_strerror(res));

        // ניקוי תמיד נדרש
        curl_easy_cleanup(curl);
    }
    
    curl_global_cleanup();

    return 0;
}
```
בדוגמה למעלה, החלף את `"http://example.com/resource"`, `"username"`, ו-"password" עם ה-URL, שם המשתמש והסיסמה האמיתיים שלך.

קוד זה מאתחל אובייקט `CURL`, מגדיר את ה-URL, מפעיל את אימות HTTP הבסיסי ומציין את האישורים. לאחר מכן הוא שולח את הבקשה ומנקה אחרי עצמו. אם הבקשה מצליחה, המשאב המבוקש נאסף; אם ישנה שגיאה, היא תודפס ל-stderr.

פלט לדוגמה (בהנחה שהאימות וגישה למשאב הצליחו) עשוי שלא להופיע ישירות על ידי התוכנית, מפני שהדוגמה מדגימה בעיקר את שליחת הבקשה. כדי להדפיס את התגובה, היית מרחיב את התוכנית כדי לטפל בנתוני תגובת ה-HTTP.

## הבנה עמוקה יותר:
שליחת בקשות HTTP עם אימות בסיסי ב-C, כפי שהוצג, מנצלת את ספריית libcurl בשל חוסנה ופשטותה. מסורתית, יצירת בקשות HTTP טהורות ב-C ללא ספריות כאלו הייתה מסורבלת ורגישה לשגיאות, כוללת תכנות תקעים ברמה נמוכה ובנייה ידנית של כותרות HTTP.

האימות הבסיסי בפני עצמו הוא שיטה מימי הראשית של האינטרנט. הוא שולח אישורים בפורמט ניתן לפענוח בקלות (Base64), המהווה אי-ביטחון עצמי בערוצים טקסט פשוטים. יישומים מודרניים לעיתים קרובות מעדיפים שיטות אימות בטוחות יותר, כגון OAuth 2.0 או JWT (אסימוני רשת ג'ייסון), במיוחד עבור נתונים רגישים.

עם זאת, עבור מערכות פנימיות, פחות קריטיות, או סקריפטים מהירים ומלוכלכים שבהם הנוחות חשובה יותר מהרגישות לביטחון, האימות הבסיסי עדיין בשימוש. בנוסף, כאשר משולב עם חיבורים מוצפנים (HTTPS), הפשטות שלו הופכת ליתרון לפיתוח, בדיקות, או אוטומציה מהירה שבהן מנגנוני אבטחה מורכבים יותר אינם נחוצים בהכרח.

בהקשרים בהם אבטחת חוד הוא לא למשא ומתן, יש להעדיף אלטרנטיבות כדוגמת אימות בסיס אסימונים. עם זאת, הבנה איך לממש אימות בסיסי ב-C דרך libcurl מספקת כישור בסיסי שניתן להתאים לשיטות אימות ופרוטוקולים שונים, משקפת את הפשרות המורכבות בין אבטחה, נוחות, ודרישות היישום בפיתוח אינטרנט.
