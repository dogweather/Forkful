---
aliases:
- /he/go/downloading-a-web-page/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:56:45.969596-07:00
description: "\u05D4\u05D5\u05E8\u05D3\u05EA \u05D3\u05E3 \u05D0\u05D9\u05E0\u05D8\
  \u05E8\u05E0\u05D8 \u05D4\u05D9\u05D0 \u05D1\u05E2\u05E6\u05DD \u05D4\u05D1\u05D0\
  \u05EA \u05EA\u05D5\u05DB\u05DF \u05D4-HTML \u05E9\u05DC \u05D3\u05E3 \u05D0\u05D9\
  \u05E0\u05D8\u05E8\u05E0\u05D8 \u05D1\u05D0\u05DE\u05E6\u05E2\u05D5\u05EA \u05E4\
  \u05E8\u05D5\u05D8\u05D5\u05E7\u05D5\u05DC HTTP/HTTPS. \u05DE\u05EA\u05DB\u05E0\u05EA\
  \u05D9\u05DD \u05DC\u05E2\u05D9\u05EA\u05D9\u05DD \u05E7\u05E8\u05D5\u05D1\u05D5\
  \u05EA \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DC\u05E6\u05D5\u05E8\
  \u05DA \u05D2\u05E8\u05D9\u05E4\u05EA \u05D0\u05EA\u05E8\u05D9\u05DD, \u05E0\u05D9\
  \u05EA\u05D5\u05D7 \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD, \u05D0\u05D5\u2026"
lastmod: 2024-02-18 23:08:52.338253
model: gpt-4-0125-preview
summary: "\u05D4\u05D5\u05E8\u05D3\u05EA \u05D3\u05E3 \u05D0\u05D9\u05E0\u05D8\u05E8\
  \u05E0\u05D8 \u05D4\u05D9\u05D0 \u05D1\u05E2\u05E6\u05DD \u05D4\u05D1\u05D0\u05EA\
  \ \u05EA\u05D5\u05DB\u05DF \u05D4-HTML \u05E9\u05DC \u05D3\u05E3 \u05D0\u05D9\u05E0\
  \u05D8\u05E8\u05E0\u05D8 \u05D1\u05D0\u05DE\u05E6\u05E2\u05D5\u05EA \u05E4\u05E8\
  \u05D5\u05D8\u05D5\u05E7\u05D5\u05DC HTTP/HTTPS. \u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\
  \u05DD \u05DC\u05E2\u05D9\u05EA\u05D9\u05DD \u05E7\u05E8\u05D5\u05D1\u05D5\u05EA\
  \ \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DC\u05E6\u05D5\u05E8\u05DA\
  \ \u05D2\u05E8\u05D9\u05E4\u05EA \u05D0\u05EA\u05E8\u05D9\u05DD, \u05E0\u05D9\u05EA\
  \u05D5\u05D7 \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD, \u05D0\u05D5\u2026"
title: "\u05D4\u05D5\u05E8\u05D3\u05EA \u05D3\u05E3 \u05D0\u05D9\u05E0\u05D8\u05E8\
  \u05E0\u05D8"
---

{{< edit_this_page >}}

## מה ולמה?

הורדת דף אינטרנט היא בעצם הבאת תוכן ה-HTML של דף אינטרנט באמצעות פרוטוקול HTTP/HTTPS. מתכנתים לעיתים קרובות עושים זאת לצורך גריפת אתרים, ניתוח נתונים, או פשוט כדי לפעול באופן תוכניתי עם אתרי אינטרנט כדי לאוטמט פעולות.

## איך לעשות:

ב-GO, ספריית התקן מספקת כלים חזקים לבקשות אינטרנט, בעיקר החבילה `net/http`. להורדת דף אינטרנט, אנו משתמשים בעיקר בשיטת `http.Get`. הנה דוגמה בסיסית:

```go
package main

import (
    "fmt"
    "io/ioutil"
    "net/http"
)

func main() {
    url := "http://example.com"
    response, err := http.Get(url)
    if err != nil {
        fmt.Println("Error:", err)
        return
    }
    defer response.Body.Close()

    body, err := ioutil.ReadAll(response.Body)
    if err != nil {
        fmt.Println("Error reading body:", err)
        return
    }

    fmt.Println(string(body))
}
```

פלט לדוגמה יכול להיות תוכן ה-HTML של `http://example.com`, שהוא דוגמה בסיסית של דף אינטרנט:

```
<!doctype html>
<html>
<head>
    <title>Example Domain</title>
...
</html>
```

תוכנית פשוטה זו מבצעת בקשת HTTP GET ל-URL שצוין, ולאחר מכן קוראת ומדפיסה את גוף התגובה.

הערה: בתכנות GO עכשווי, `ioutil.ReadAll` נחשב למיושן מאז GO 1.16 לטובת `io.ReadAll`.

## צלילה עמוקה

לשפת GO יש פילוסופיית עיצוב שמדגישה פשטות, יעילות וטיפול אמין בשגיאות. כאשר מדובר בתכנות רשת, ובפרט להורדת דפי אינטרנט, ספריית התקן של GO, בעיקר `net/http`, מעוצבת ביעילות לטפל בפעולות בקשה ותגובה של HTTP.

הגישה לבקשות רשת ב-GO נשענת על מוצא השפה, שואבת מושגים מקודמות אך משפרת משמעותית את היעילות והפשטות. בפעולות הורדת תוכן, מודל הקבילות של GO באמצעות גורוטינות הופך אותה לכלי עוצמתי במיוחד לבצע בקשות HTTP אסינכרוניות, ולהתמודד עם אלפי בקשות במקביל בקלות.

בעבר, מתכנתים הסתמכו במידה רבה על ספריות צד שלישי בשפות אחרות לבקשות HTTP פשוטות, אך ספריית התקן של GO מבטלת בעצם את הצורך הזה לרוב המקרים הנפוצים. למרות שקיימות חלופות וחבילות נוספות מקיפות יותר לתרחישים מורכבים, כמו `Colly` לגריפת אתרים, החבילה המקורית `net/http` לרוב מספיקה להורדת דפי אינטרנט, הופכת את GO לבחירה מושכת למפתחים המחפשים פתרון מובנה ללא יתרות.

בהשוואה לשפות אחרות, GO מספקת דרך נוחה וביצועית במיוחד לבצע פעולות רשת, מה שמדגיש את פילוסופיית השפה של לעשות יותר עם פחות. אף על פי שקיימות אלטרנטיבות טובות יותר למשימות מיוחדות, תכונות הבנויות ב-GO מציעות שיווי משקל בין נוחות שימוש לבינה, הופכות אותה לאופציה מפתה להורדת תוכן אינטרנטי.
