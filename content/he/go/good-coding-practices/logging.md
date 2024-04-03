---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:59:57.720255-07:00
description: "\u05DC\u05D5\u05D2\u05D9\u05E0\u05D2 \u05D1\u05E4\u05D9\u05EA\u05D5\u05D7\
  \ \u05EA\u05D5\u05DB\u05E0\u05D4 \u05D4\u05D5\u05D0 \u05D4\u05EA\u05D4\u05DC\u05D9\
  \u05DA \u05E9\u05DC \u05E8\u05D9\u05E9\u05D5\u05DD \u05DE\u05D9\u05D3\u05E2 \u05D0\
  \u05D5\u05D3\u05D5\u05EA \u05D1\u05D9\u05E6\u05D5\u05E2\u05D9 \u05EA\u05D5\u05DB\
  \u05E0\u05D9\u05EA, \u05E9\u05EA\u05D5\u05DB\u05E0\u05DF \u05DC\u05E2\u05E7\u05D5\
  \u05D1 \u05D0\u05D7\u05E8 \u05D4\u05EA\u05E0\u05D4\u05D2\u05D5\u05EA\u05D4 \u05D5\
  \u05DC\u05D0\u05D1\u05D7\u05DF \u05D1\u05E2\u05D9\u05D5\u05EA. \u05DE\u05EA\u05DB\
  \u05E0\u05EA\u05D9\u05DD \u05DE\u05D9\u05D9\u05E9\u05DE\u05D9\u05DD \u05DC\u05D5\
  \u05D2\u05D9\u05E0\u05D2 \u05E2\u05DC \u05DE\u05E0\u05EA \u05DC\u05E0\u05D8\u05E8\
  \ \u05D0\u05EA \u05D1\u05D9\u05E6\u05D5\u05E2\u05D9\u2026"
lastmod: '2024-03-13T22:44:38.501862-06:00'
model: gpt-4-0125-preview
summary: "\u05DC\u05D5\u05D2\u05D9\u05E0\u05D2 \u05D1\u05E4\u05D9\u05EA\u05D5\u05D7\
  \ \u05EA\u05D5\u05DB\u05E0\u05D4 \u05D4\u05D5\u05D0 \u05D4\u05EA\u05D4\u05DC\u05D9\
  \u05DA \u05E9\u05DC \u05E8\u05D9\u05E9\u05D5\u05DD \u05DE\u05D9\u05D3\u05E2 \u05D0\
  \u05D5\u05D3\u05D5\u05EA \u05D1\u05D9\u05E6\u05D5\u05E2\u05D9 \u05EA\u05D5\u05DB\
  \u05E0\u05D9\u05EA, \u05E9\u05EA\u05D5\u05DB\u05E0\u05DF \u05DC\u05E2\u05E7\u05D5\
  \u05D1 \u05D0\u05D7\u05E8 \u05D4\u05EA\u05E0\u05D4\u05D2\u05D5\u05EA\u05D4 \u05D5\
  \u05DC\u05D0\u05D1\u05D7\u05DF \u05D1\u05E2\u05D9\u05D5\u05EA."
title: "\u05E8\u05D9\u05E9\u05D5\u05DD"
weight: 17
---

## איך לעשות:
בגו, ניתן ליישם לוגינג באמצעות החבילה הסטנדרטית `log`. חבילה זו מספקת יכולות לוגינג פשוטות, כמו כתיבה לפלט הסטנדרטי או לקבצים. בואו נתחיל עם דוגמה בסיסית של לוגינג לפלט הסטנדרטי:

```go
package main

import (
	"log"
)

func main() {
	log.Println("This is a basic log entry.")
}
```

פלט:
```
2009/11/10 23:00:00 This is a basic log entry.
```

החותמת זמן בתחילת רשומת הלוג מתווספת אוטומטית על ידי החבילה `log`. לאחר מכן, בואו נבחן איך לתעד לוגים לקובץ במקום לפלט הסטנדרטי:

```go
package main

import (
	"log"
	"os"
)

func main() {
	file, err := os.OpenFile("app.log", os.O_CREATE|os.O_APPEND|os.O_WRONLY, 0666)
	if err != nil {
		log.Fatal(err)
	}
	defer file.Close()

	log.SetOutput(file)
	log.Println("This log entry goes to a file.")
}
```

כעת, בואו ניישם מקרה שימוש מתקדם יותר: התאמה אישית של פורמט הלוגינג. גו מאפשרת לך ליצור לוגר מותאם אישית עם `log.New()`:

```go
package main

import (
	"log"
	"os"
)

func main() {
	logger := log.New(os.Stdout, "CUSTOM LOG: ", log.Ldate|log.Ltime|log.Lshortfile)
	logger.Println("This is a custom log message.")
}
```

פלט:
```
CUSTOM LOG: 2009/11/10 23:00:00 main.go:11: This is a custom log message.
```

דוגמה זו מוסיפה לכל הודעת לוג את הקידומת "CUSTOM LOG: " וכוללת את התאריך, השעה ומיקום קובץ המקור.

##  צלילה עמוקה
חבילת `log` של ספריית התקנים של גו היא פשוטה ומספיקה למגוון יישומים, אך היא חסרה כמה מהתכונות המתקדמות הנמצאות בספריות לוגינג של גורמים שלישיים, כגון לוגינג מובנה, סיבוב לוגים, ולוגינג מבוסס רמות. חבילות כמו `zap` ו-`logrus` מציעות את תכונות אלו המתקדמות ונחשבות בקהילת גו לבעלות ביצועים וגמישות גבוהים.

לוגינג מבני, לדוגמה, מאפשר לך לתעד נתונים בפורמט מבנה (כמו JSON), שהוא במיוחד שימושי ליישומים מבוססי ענן מודרניים שבהם הלוגים עשויים להינתח על ידי מגוון כלים או שירותים. `zap`, במיוחד, ידועה בביצועי הגבוהים שלה ונטל ההקצאה הנמוך, ההופכים אותה למתאימה ליישומים שבהם המהירות והיעילות הם קריטיים.

בהיסטוריה, הלוגינג בגו התפתח באופן משמעותי מאז הופעת השפה. גרסאות הראשונות של גו סיפקו את היכולות הבסיסיות ללוגינג שאנו רואים בחבילת `log`. עם זאת, ככל שהשפה זכתה לפופולריות וככל שהסיבוכיות של היישומים שנכתבו בגו גדלה, הקהילה החלה לפתח ספריות לוגינג מתוחכמות יותר כדי לעמוד בצרכים שלהם. כיום, בעוד שחבילת `log` הסטנדרטית נותרת אופציה ויעילה ליישומים פשוטים, מפתחים רבים פונים לפתרונות של גורמים שלישיים אלה לצורך דרישות לוגינג מורכבות יותר.
