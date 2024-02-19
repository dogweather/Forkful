---
aliases:
- /he/arduino/comparing-two-dates/
date: 2024-01-20 17:32:39.935977-07:00
description: "\u05DE\u05D4 \u05D6\u05D4 \u05D4\u05E9\u05D5\u05D5\u05D0\u05EA \u05E9\
  \u05EA\u05D9 \u05EA\u05D0\u05E8\u05D9\u05DB\u05D9\u05DD \u05D5\u05DC\u05DE\u05D4\
  \ \u05D6\u05D4 \u05D7\u05E9\u05D5\u05D1? \u05D4\u05E9\u05D5\u05D5\u05D0\u05EA \u05E9\
  \u05EA\u05D9 \u05EA\u05D0\u05E8\u05D9\u05DB\u05D9\u05DD \u05DE\u05D0\u05E4\u05E9\
  \u05E8\u05EA \u05DC\u05E0\u05D5 \u05DC\u05DE\u05D3\u05D5\u05D3 \u05E4\u05E8\u05E7\
  \u05D9 \u05D6\u05DE\u05DF \u05D5\u05DC\u05D1\u05E6\u05E2 \u05E4\u05E2\u05D5\u05DC\
  \u05D5\u05EA \u05D1\u05D4\u05EA\u05D0\u05DD \u05DC\u05DC\u05D5\u05D7 \u05D4\u05E9\
  \u05E0\u05D4. \u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD\
  \ \u05D6\u05D0\u05EA \u05DC\u05E9\u05DC\u05DC \u05E1\u05D9\u05D1\u05D5\u05EA, \u05DB\
  \u05DE\u05D5 \u05DC\u05E2\u05E7\u05D5\u05D1\u2026"
lastmod: 2024-02-18 23:08:53.127742
model: gpt-4-1106-preview
summary: "\u05DE\u05D4 \u05D6\u05D4 \u05D4\u05E9\u05D5\u05D5\u05D0\u05EA \u05E9\u05EA\
  \u05D9 \u05EA\u05D0\u05E8\u05D9\u05DB\u05D9\u05DD \u05D5\u05DC\u05DE\u05D4 \u05D6\
  \u05D4 \u05D7\u05E9\u05D5\u05D1? \u05D4\u05E9\u05D5\u05D5\u05D0\u05EA \u05E9\u05EA\
  \u05D9 \u05EA\u05D0\u05E8\u05D9\u05DB\u05D9\u05DD \u05DE\u05D0\u05E4\u05E9\u05E8\
  \u05EA \u05DC\u05E0\u05D5 \u05DC\u05DE\u05D3\u05D5\u05D3 \u05E4\u05E8\u05E7\u05D9\
  \ \u05D6\u05DE\u05DF \u05D5\u05DC\u05D1\u05E6\u05E2 \u05E4\u05E2\u05D5\u05DC\u05D5\
  \u05EA \u05D1\u05D4\u05EA\u05D0\u05DD \u05DC\u05DC\u05D5\u05D7 \u05D4\u05E9\u05E0\
  \u05D4. \u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\
  \u05D0\u05EA \u05DC\u05E9\u05DC\u05DC \u05E1\u05D9\u05D1\u05D5\u05EA, \u05DB\u05DE\
  \u05D5 \u05DC\u05E2\u05E7\u05D5\u05D1\u2026"
title: "\u05D4\u05E9\u05D5\u05D5\u05D0\u05EA \u05E9\u05EA\u05D9 \u05EA\u05D0\u05E8\
  \u05D9\u05DB\u05D9\u05DD"
---

{{< edit_this_page >}}

## What & Why?
מה זה השוואת שתי תאריכים ולמה זה חשוב? השוואת שתי תאריכים מאפשרת לנו למדוד פרקי זמן ולבצע פעולות בהתאם ללוח השנה. תכנתים עושים זאת לשלל סיבות, כמו לעקוב אחר זמנים של אירועים או לממש לוחות זמנים אוטומטיים.

## How to:
להלן דוגמה של קוד להשוואת שתי תאריכים בעזרת Arduino:

```Arduino
#include <TimeLib.h>

void setup() {
  Serial.begin(9600);
  // Set up the two dates to compare
  time_t firstDate = now(); // Assuming now() returns the current date and time
  delay(10000); // Delay for 10 seconds to simulate time passing
  time_t secondDate = now();

  // Compare the two dates
  if(secondDate > firstDate) {
    Serial.println("The second date is later than the first date.");
  } else {
    Serial.println("The dates are either the same, or something went wrong.");
  }
}

void loop() {
  // ... other code if needed
}
```

תוצאת הדוגמה תהיה הדפסה שהתאריך השני מאוחר יותר מהראשון או שהם זהים.

## Deep Dive:
בעולם ה-Arduino, נדיר שמשתמשים בפונקציות תאריך ושעה מורכבות, בדרך כלל בגלל החומרה של Arduino שאינה תומכת בצורה טבעית בעקביות זמן (RTC - Real Time Clock). יש להשתמש בספריות כמו TimeLib לטיפול בתאריכים ובזמנים. חלופה לכך היא שימוש במודול RTC חיצוני כמו DS3231. עבור יישומים מתקדמים, ייתכן שיתעללו בפונקציות סטנדרטיות של C/C++ לניהול זמן או שיבנו מנגנון מותאם אישית.

## See Also:
- ספריית TimeLib: https://www.pjrc.com/teensy/td_libs_Time.html
- מודול RTC DS3231: https://learn.adafruit.com/adafruit-ds3231-precision-rtc-breakout
- דוקומנטציה של זמן ב-C/C++: https://en.cppreference.com/w/c/chrono
- דוגמאות נוספות לעבודה עם זמנים ב-Arduino: https://www.arduino.cc/en/Tutorial/BuiltInExamples
