---
title:                "מציאת אורך מחרוזת"
date:                  2024-01-20T17:47:04.589362-07:00
model:                 gpt-4-1106-preview
simple_title:         "מציאת אורך מחרוזת"
programming_language: "Arduino"
category:             "Arduino"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/arduino/finding-the-length-of-a-string.md"
---

{{< edit_this_page >}}

## What & Why?
מה זה אורך המחרוזת ולמה זה חשוב? אורך המחרוזת מספר לנו כמה תווים יש בה. תכניתנים משתמשים בזה לוודא שהכניסה תקינה, לעבד נתונים, ולשלוט על זרימות לוגיות.

## How to:
```Arduino
String myText = "שלום עולם";
int textLength = myText.length();

Serial.begin(9600);
Serial.print("אורך המחרוזת: ");
Serial.println(textLength); // יודפס: אורך המחרוזת: 10
```
בדוגמה, אנחנו משתמשים ב-`length()` כדי לקבוע את אורך המחרוזת, ואז מדפיסים אותו דרך ה-Serial Monitor.

## Deep Dive
בהיסטוריה של שפות תכנות, אורך המחרוזת תמיד היה נושא חשוב. בשפות כמו C, אורך מחרוזת נקבע על ידי חיפוש אחר התו המיוחד '\0'. בארדואינו, שמשתמש בשפת C++, יש למחלקה `String` מתודות מובנות כמו `length()`. חלפים ל-`length()` עלולים לכלול פונקציות כמו `strlen()` למערכי תווים מסוג char. המימוש של `length()` בעצם סופר את התווים עד שהוא מגיע לסיומת של המחרוזת.

## See Also
- תיעוד רשמי למתודת `length()` למחרוזות בארדואינו: [Arduino Reference](https://www.arduino.cc/reference/en/language/variables/data-types/string/functions/length/)
- הבדלים בין מחלקת `String` למערכי `char` בארדואינו: [Arduino String vs. char](https://www.arduino.cc/en/Tutorial/BuiltInExamples/StringCharacters)
- מידע נוסף על קריאה וכתיבה דרך ה-Serial Monitor: [Arduino Serial](https://www.arduino.cc/reference/en/language/functions/communication/serial/)