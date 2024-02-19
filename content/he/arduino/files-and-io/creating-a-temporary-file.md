---
aliases:
- /he/arduino/creating-a-temporary-file/
date: 2024-01-20 17:39:50.013296-07:00
description: "\u05D9\u05E6\u05D9\u05E8\u05EA \u05E7\u05D5\u05D1\u05E5 \u05D6\u05DE\
  \u05E0\u05D9 \u05D4\u05D9\u05D0 \u05EA\u05D4\u05DC\u05D9\u05DA \u05E9\u05D1\u05D5\
  \ \u05E0\u05D5\u05E6\u05E8 \u05E7\u05D5\u05D1\u05E5 \u05DC\u05E9\u05D9\u05DE\u05D5\
  \u05E9 \u05D7\u05D3 \u05E4\u05E2\u05DE\u05D9 \u05D0\u05D5 \u05D6\u05DE\u05E0\u05D9\
  \ \u05D1\u05EA\u05D5\u05DB\u05E0\u05D9\u05EA. \u05EA\u05DB\u05E0\u05D9\u05EA\u05D9\
  \u05D9\u05DD \u05DC\u05E2\u05D9\u05EA\u05D9\u05DD \u05E7\u05E8\u05D5\u05D1\u05D5\
  \u05EA \u05DE\u05E9\u05EA\u05DE\u05E9\u05D9\u05DD \u05D1\u05E7\u05D1\u05E6\u05D9\
  \u05DD \u05D6\u05DE\u05E0\u05D9\u05D9\u05DD \u05DB\u05D3\u05D9 \u05DC\u05D0\u05D7\
  \u05E1\u05DF \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD \u05DC\u05E6\u05D5\u05E8\u05DA\
  \ \u05E2\u05D9\u05D1\u05D5\u05D3 \u05D6\u05DE\u05E0\u05D9 \u05D0\u05D5\u2026"
lastmod: 2024-02-18 23:08:53.135210
model: gpt-4-1106-preview
summary: "\u05D9\u05E6\u05D9\u05E8\u05EA \u05E7\u05D5\u05D1\u05E5 \u05D6\u05DE\u05E0\
  \u05D9 \u05D4\u05D9\u05D0 \u05EA\u05D4\u05DC\u05D9\u05DA \u05E9\u05D1\u05D5 \u05E0\
  \u05D5\u05E6\u05E8 \u05E7\u05D5\u05D1\u05E5 \u05DC\u05E9\u05D9\u05DE\u05D5\u05E9\
  \ \u05D7\u05D3 \u05E4\u05E2\u05DE\u05D9 \u05D0\u05D5 \u05D6\u05DE\u05E0\u05D9 \u05D1\
  \u05EA\u05D5\u05DB\u05E0\u05D9\u05EA. \u05EA\u05DB\u05E0\u05D9\u05EA\u05D9\u05D9\
  \u05DD \u05DC\u05E2\u05D9\u05EA\u05D9\u05DD \u05E7\u05E8\u05D5\u05D1\u05D5\u05EA\
  \ \u05DE\u05E9\u05EA\u05DE\u05E9\u05D9\u05DD \u05D1\u05E7\u05D1\u05E6\u05D9\u05DD\
  \ \u05D6\u05DE\u05E0\u05D9\u05D9\u05DD \u05DB\u05D3\u05D9 \u05DC\u05D0\u05D7\u05E1\
  \u05DF \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD \u05DC\u05E6\u05D5\u05E8\u05DA \u05E2\
  \u05D9\u05D1\u05D5\u05D3 \u05D6\u05DE\u05E0\u05D9 \u05D0\u05D5\u2026"
title: "\u05D9\u05E6\u05D9\u05E8\u05EA \u05E7\u05D5\u05D1\u05E5 \u05D6\u05DE\u05E0\
  \u05D9"
---

{{< edit_this_page >}}

## מה ולמה?
יצירת קובץ זמני היא תהליך שבו נוצר קובץ לשימוש חד פעמי או זמני בתוכנית. תכניתיים לעיתים קרובות משתמשים בקבצים זמניים כדי לאחסן נתונים לצורך עיבוד זמני או כחלק ממנגנוני לוגיקה לתיקון באגים.

## איך לעשות:
בעוד שבשפות תכנות אחרות יצירת קובץ זמני היא פעולה נפוצה, בארדואינו הנושא יותר מורכב משום שרוב הלוחות אינם מכילים מערכת קבצים או זיכרון מרובה. במקום זאת, ניתן ליצור קובץ זמני בכרטיס זיכרון SD עם המציאת כרטיס SD והפינים הנכונים.

```Arduino
#include <SPI.h>
#include <SD.h>

File tempFile;

void setup() {
  Serial.begin(9600);
  // הקפד לשנות את הפין לזה של חיבור ה-SD שלך
  if (!SD.begin(4)) {
    Serial.println("התחברות ל-SD נכשלה");
    return;
  }

  // יצירת קובץ זמני
  tempFile = SD.open("temp.txt", FILE_WRITE);
  if (tempFile) {
    tempFile.println("המדריך שלך לארדואינו");
    tempFile.close(); // חשוב לסגור אחרי השימוש
  } else {
    Serial.println("יצירת קובץ נכשלה");
  }
}

void loop() {
  // קידוד הלולאה שלך כאן
}
```

## עיון נוסף:
ההיסטוריה של קבצים זמניים החלה עוד בתקופת החלונות המוקדמים, כאשר מערכות הפעלה נעזרו בהם כדי לנהל זיכרון וכחלק מגיבוי נתונים. בארדואינו, בשל המגבלות המסוימות של החומרה, יצירת 'קובץ זמני' אינה פעולה שבשגרה והיא דורשת רכיבים חיצוניים מוספים כגון מודול כרטיס SD.

כאשר אנו משתמשים בקבצים זמניים בארדואינו, קריטי לדאוג שהקובץ ייסגר לאחר השימוש כדי למנוע פגיעה בכרטיס ה-SD או אבדן נתונים. זיכרו שבשונה ממחשב רגיל, הארדואינו רץ קוד שקוע ולכן יש לתכנת בזהירות רבה יחסית.

אפשרויות חלופיות כוללות שמירת משתנים זמניים ב-ZRAM או בשימוש ב-NVRAM או בזיכרון EEPROM, אך יש לשקול את נפח הכתיבה לזיכרון הזה, שכן הוא מוגבל.

## לקרוא גם:
- תיעוד של חבילת SD של ארדואינו: https://www.arduino.cc/en/Reference/SD
- מדריך להתחברות כרטיס SD לארדואינו: https://www.arduino.cc/en/Guide/MKRSD
- מידע נוסף על EEPROM בארדואינו: https://www.arduino.cc/en/Reference/EEPROM
