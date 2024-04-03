---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:59:05.047658-07:00
description: "\u05D0\u05D9\u05E0\u05D8\u05E8\u05E4\u05D5\u05DC\u05E6\u05D9\u05D4 \u05E9\
  \u05DC \u05DE\u05D7\u05E8\u05D5\u05D6\u05D5\u05EA \u05D4\u05D9\u05D0 \u05E9\u05D9\
  \u05D8\u05D4 \u05DC\u05D1\u05E0\u05D9\u05D9\u05EA \u05DE\u05D7\u05E8\u05D5\u05D6\
  \u05D5\u05EA \u05D4\u05DE\u05E9\u05DC\u05D1\u05D5\u05EA \u05DE\u05E9\u05EA\u05E0\
  \u05D9\u05DD, \u05D5\u05DE\u05D0\u05E4\u05E9\u05E8\u05EA \u05D9\u05E6\u05D9\u05E8\
  \u05EA \u05DE\u05D7\u05E8\u05D5\u05D6\u05D5\u05EA \u05D3\u05D9\u05E0\u05DE\u05D9\
  \u05D5\u05EA. \u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\
  \u05DD \u05D6\u05D0\u05EA \u05E2\u05DC \u05DE\u05E0\u05EA \u05DC\u05D4\u05EA\u05D0\
  \u05D9\u05DD \u05D4\u05D5\u05D3\u05E2\u05D5\u05EA, \u05DC\u05D1\u05E0\u05D5\u05EA\
  \ URLs, \u05DC\u05D9\u05E6\u05D5\u05E8\u2026"
lastmod: '2024-03-13T22:44:38.464602-06:00'
model: gpt-4-0125-preview
summary: "\u05D0\u05D9\u05E0\u05D8\u05E8\u05E4\u05D5\u05DC\u05E6\u05D9\u05D4 \u05E9\
  \u05DC \u05DE\u05D7\u05E8\u05D5\u05D6\u05D5\u05EA \u05D4\u05D9\u05D0 \u05E9\u05D9\
  \u05D8\u05D4 \u05DC\u05D1\u05E0\u05D9\u05D9\u05EA \u05DE\u05D7\u05E8\u05D5\u05D6\
  \u05D5\u05EA \u05D4\u05DE\u05E9\u05DC\u05D1\u05D5\u05EA \u05DE\u05E9\u05EA\u05E0\
  \u05D9\u05DD, \u05D5\u05DE\u05D0\u05E4\u05E9\u05E8\u05EA \u05D9\u05E6\u05D9\u05E8\
  \u05EA \u05DE\u05D7\u05E8\u05D5\u05D6\u05D5\u05EA \u05D3\u05D9\u05E0\u05DE\u05D9\
  \u05D5\u05EA."
title: "\u05D0\u05D9\u05E0\u05D8\u05E8\u05E4\u05D5\u05DC\u05E6\u05D9\u05D4 \u05E9\u05DC\
  \ \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA"
weight: 8
---

## איך לעשות:
ב-Go, אינטרפולציה של מחרוזות מתבצעת לרוב באמצעות חבילת ה-`fmt`, בעיקר עם הפונקציה `Sprintf`, שמאפשרת לך להזריק משתנים לתוך מחרוזת על ידי ציון פקודות עיצוב. הפקודות הן מצייני מקום במחרוזת העיצוב והן מוחלפות בערכי המשתנים הנתונים. כך משתמשים בה:

```go
package main

import (
    "fmt"
)

func main() {
    name := "Jane"
    age := 28

    // שימוש ב-Sprintf לאינטרפולציה של מחרוזת
    message := fmt.Sprintf("שלום, שמי %s ואני בן %d.", name, age)
    fmt.Println(message) // פלט: שלום, שמי Jane ואני בן 28.
}
```

לתשומת לבך, `%s` משמש למחרוזות, ו-`%d` למספרים שלמים. התיעוד של חבילת ה-`fmt` מספק רשימה מקיפה של פקודות עיצוב לסוגי נתונים שונים.

## צלילה עמוקה
המושג של אינטרפולציה של מחרוזות קיים בשפות תכנות רבות, אף על פי שהתחבירים והיכולות שונים. ב-Go, למרות שהפונקציה `Sprintf` של חבילת ה-`fmt` היא השיטה הנפוצה ביותר המשמשת, ייתכן שהיא לא תמיד הכי יעילה, במיוחד לקיטובים פשוטים או כאשר עובדים בקוד הדורש רגישות גבוהה לביצועים.

חבילת ה-`fmt` משתמשת ברפלקציה כדי לפרש באופן דינמי את סוגי המשתנים בזמן ריצה, מה שמעניק גמישות אך גם גורם לעומס. לסיטואציות בהן הביצועים קריטיים, קיטוב ישיר של מחרוזות או הטיפוס `strings.Builder` עשויים להציע אלטרנטיבות טובות יותר. קיטוב ישיר הוא פשוט אך עלול להיות מסורבל עם מספר משתנים. הטיפוס `strings.Builder`, מצד שני, מספק דרך יעילה וקריאה יותר לבנות מחרוזות מורכבות בלולאה או כאשר מתמודדים עם מספר משתנים:

```go
var sb strings.Builder
sb.WriteString("שלום, שמי ")
sb.WriteString(name)
sb.WriteString(" ואני בן ")
sb.WriteString(strconv.Itoa(age))
sb.WriteString(".")
message := sb.String()

fmt.Println(message) // מוציא לפועל את אותו הדבר כמו קודם
```

לבסוף, הבחירה בין `fmt.Sprintf`, קיטוב ישיר, ו-`strings.Builder` תלויה בדרישות הספציפיות של היישום שלך, כגון מורכבות המחרוזת הנבנית והתחשיבים בביצועים.
