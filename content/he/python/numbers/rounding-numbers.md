---
aliases:
- /he/python/rounding-numbers/
date: 2024-01-26 03:46:59.695763-07:00
description: "\u05E2\u05D9\u05D2\u05D5\u05DC \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD\
  \ \u05E4\u05D9\u05E8\u05D5\u05E9\u05D5 \u05D4\u05EA\u05D0\u05DE\u05EA\u05DD \u05DC\
  \u05D4\u05D9\u05D5\u05EA \u05E7\u05E8\u05D5\u05D1\u05D9\u05DD \u05D9\u05D5\u05EA\
  \u05E8 \u05DC\u05E2\u05E8\u05DA \u05E4\u05E9\u05D5\u05D8 \u05D0\u05D5 \u05DE\u05E9\
  \u05DE\u05E2\u05D5\u05EA\u05D9 \u05D9\u05D5\u05EA\u05E8. \u05DE\u05EA\u05DB\u05E0\
  \u05EA\u05D9\u05DD \u05DE\u05E2\u05D2\u05DC\u05D9\u05DD \u05DE\u05E1\u05E4\u05E8\
  \u05D9\u05DD \u05DB\u05D3\u05D9 \u05DC\u05E4\u05E9\u05D8 \u05EA\u05D5\u05E6\u05D0\
  \u05D5\u05EA, \u05DC\u05D4\u05D2\u05D1\u05D9\u05DC \u05DE\u05E7\u05D5\u05DE\u05D5\
  \u05EA \u05E2\u05E9\u05E8\u05D5\u05E0\u05D9\u05D9\u05DD \u05DC\u05E6\u05D5\u05E8\
  \u05DA \u05D4\u05E6\u05D2\u05D4, \u05D0\u05D5\u2026"
lastmod: 2024-02-18 23:08:52.431395
model: gpt-4-0125-preview
summary: "\u05E2\u05D9\u05D2\u05D5\u05DC \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD \u05E4\
  \u05D9\u05E8\u05D5\u05E9\u05D5 \u05D4\u05EA\u05D0\u05DE\u05EA\u05DD \u05DC\u05D4\
  \u05D9\u05D5\u05EA \u05E7\u05E8\u05D5\u05D1\u05D9\u05DD \u05D9\u05D5\u05EA\u05E8\
  \ \u05DC\u05E2\u05E8\u05DA \u05E4\u05E9\u05D5\u05D8 \u05D0\u05D5 \u05DE\u05E9\u05DE\
  \u05E2\u05D5\u05EA\u05D9 \u05D9\u05D5\u05EA\u05E8. \u05DE\u05EA\u05DB\u05E0\u05EA\
  \u05D9\u05DD \u05DE\u05E2\u05D2\u05DC\u05D9\u05DD \u05DE\u05E1\u05E4\u05E8\u05D9\
  \u05DD \u05DB\u05D3\u05D9 \u05DC\u05E4\u05E9\u05D8 \u05EA\u05D5\u05E6\u05D0\u05D5\
  \u05EA, \u05DC\u05D4\u05D2\u05D1\u05D9\u05DC \u05DE\u05E7\u05D5\u05DE\u05D5\u05EA\
  \ \u05E2\u05E9\u05E8\u05D5\u05E0\u05D9\u05D9\u05DD \u05DC\u05E6\u05D5\u05E8\u05DA\
  \ \u05D4\u05E6\u05D2\u05D4, \u05D0\u05D5\u2026"
title: "\u05E2\u05D9\u05D2\u05D5\u05DC \u05DE\u05E1\u05E4\u05E8\u05D9\u05DD"
---

{{< edit_this_page >}}

## מה ולמה?
עיגול מספרים פירושו התאמתם להיות קרובים יותר לערך פשוט או משמעותי יותר. מתכנתים מעגלים מספרים כדי לפשט תוצאות, להגביל מקומות עשרוניים לצורך הצגה, או למטרות מתמטיות מסוימות.

## איך לעשות:
הנה המדריך לעיגול מספרים בפייתון:

```python
# עיגול מספר לשלם הקרוב ביותר
print(round(8.67))  # פלט: 9

# עיגול מספר למספר מקומות עשרוניים נתון
print(round(8.67, 1))  # פלט: 8.7

# מספרים זוגיים מעוגלים למטה ומספרים אי-זוגיים מעוגלים למעלה כאשר הם במרחק שווה
print(round(2.5))  # פלט: 2
print(round(3.5))  # פלט: 4
```

## צלילה עמוקה
בפייתון, הפונקציה `round()` אינה רק "קוטעת" עשרוניים. באופן היסטורי, פייתון, כמו שפות רבות אחרות, נשענת על "עיגול חצי לזוגי" או "עיגול הבנקאי". זה מזער שגיאה צבורה בסכומים או ממוצעים, מה שחשוב בחישובים פיננסיים.

לחלופות, יש לכם את `math.floor()` ו-`math.ceil()` ממודול המתמטיקה של פייתון, המורידים או מעלים מספרים למספר שלם הבא. אבל אם דיוק הוא מה שאתם מחפשים, `decimal` מודול של `quantize()` מאפשר לכם לציין התנהגות עיגול.

מאחורי הקלעים, `round()` מתמודדת עם מספרים נקודה צפה בינאריים. מכיוון שחלק מהעשרוניים לא יכולים להבוטא בדיוק בבינארי, ייתכן שתתקלו בהפתעות עם דברים כמו `round(2.675, 2)` שלא יהפכו ל-`2.68` כצפוי. זהו הזמן לכנס את `decimal` או `fractions` לדיוק גבוה.

## ראו גם
- תיעוד פייתון על פונקציות מובנות: https://docs.python.org/3/library/functions.html#round
- חישוב אריתמטי שבט ונקודה צפה של Decimal: https://docs.python.org/3/library/decimal.html
- מודול המתמטיקה של פייתון: https://docs.python.org/3/library/math.html
