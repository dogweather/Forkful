---
aliases:
- /he/ruby/interpolating-a-string/
date: 2024-01-20 17:52:04.328705-07:00
description: "\u05DE\u05D9\u05DC\u05D5\u05D9 \u05EA\u05D1\u05E0\u05D9\u05EA \u05D1\
  \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA (string interpolation) \u05DE\u05D0\u05E4\u05E9\
  \u05E8 \u05DC\u05D7\u05D3\u05D5\u05E8 \u05E2\u05E8\u05DB\u05D9\u05DD \u05D0\u05D5\
  \ \u05EA\u05D5\u05E6\u05D0\u05D5\u05EA \u05E9\u05DC \u05D7\u05D9\u05E9\u05D5\u05D1\
  \u05D9\u05DD \u05D9\u05E9\u05D9\u05E8\u05D5\u05EA \u05DC\u05EA\u05D5\u05DA \u05DE\
  \u05D7\u05E8\u05D5\u05D6\u05EA \u05DE\u05D5\u05D2\u05D3\u05E8\u05EA. \u05D6\u05D4\
  \ \u05E2\u05D5\u05D6\u05E8 \u05DC\u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05DC\
  \u05D9\u05E6\u05D5\u05E8 \u05D8\u05E7\u05E1\u05D8\u05D9\u05DD \u05D3\u05D9\u05E0\
  \u05DE\u05D9\u05D9\u05DD \u05DE\u05D4\u05D9\u05E8\u05D9\u05DD\u2026"
lastmod: 2024-02-18 23:08:53.374666
model: gpt-4-1106-preview
summary: "\u05DE\u05D9\u05DC\u05D5\u05D9 \u05EA\u05D1\u05E0\u05D9\u05EA \u05D1\u05DE\
  \u05D7\u05E8\u05D5\u05D6\u05EA (string interpolation) \u05DE\u05D0\u05E4\u05E9\u05E8\
  \ \u05DC\u05D7\u05D3\u05D5\u05E8 \u05E2\u05E8\u05DB\u05D9\u05DD \u05D0\u05D5 \u05EA\
  \u05D5\u05E6\u05D0\u05D5\u05EA \u05E9\u05DC \u05D7\u05D9\u05E9\u05D5\u05D1\u05D9\
  \u05DD \u05D9\u05E9\u05D9\u05E8\u05D5\u05EA \u05DC\u05EA\u05D5\u05DA \u05DE\u05D7\
  \u05E8\u05D5\u05D6\u05EA \u05DE\u05D5\u05D2\u05D3\u05E8\u05EA. \u05D6\u05D4 \u05E2\
  \u05D5\u05D6\u05E8 \u05DC\u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05DC\u05D9\
  \u05E6\u05D5\u05E8 \u05D8\u05E7\u05E1\u05D8\u05D9\u05DD \u05D3\u05D9\u05E0\u05DE\
  \u05D9\u05D9\u05DD \u05DE\u05D4\u05D9\u05E8\u05D9\u05DD\u2026"
title: "\u05E9\u05E8\u05D1\u05D5\u05D1 \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA"
---

{{< edit_this_page >}}

## מה ולמה?
מילוי תבנית במחרוזת (string interpolation) מאפשר לחדור ערכים או תוצאות של חישובים ישירות לתוך מחרוזת מוגדרת. זה עוזר למתכנתים ליצור טקסטים דינמיים מהירים ונוחים לקריאה ולתחזוקה.

## איך לעשות:
כדי לשלב ערכים במחרוזת, נשתמש בסימן `#{}` עם משתנה או ביטוי מבוקר כלשהו בתוך מחרוזת מוקפת בגרשיים מרובעים.

```Ruby
name = "דוד"
age = 25
greeting = "שלום, אני #{name} ואני בן #{age}!"

puts greeting
#=> שלום, אני דוד ואני בן 25!
```

אפשר גם לחשב בתוך סימן המרווח:

```Ruby
price = 100
tax_rate = 0.17
total = "הסכום כולל מע"מ: #{price * (1 + tax_rate)} ש"ח"

puts total
#=> הסכום כולל מע"מ: 117.0 ש"ח
```

## טבילה עמוקה
String interpolation היא פיצ'ר שהיה כבר בשפות תכנות מסווגות כקלאסיות כמו Perl ופייתון לפני שזה הגיע לרובי. בשפות אחרות, כמו C, אתה צריך להשתמש בפונקציות מיוחדות, כמו `sprintf`. רובי עשה את זה קל ונוח עם `#{}` שאפשר להשתמש בתוך כל מחרוזת מתוך גרשיים מרובעים (`"`).

יתרון של השיטה הזאת הוא שהביטויים מתחשבים בזמן הרצה, ולכן אתה יכול להכניס לתוך הביטויים משתנים שנקבעו או השתנו במהלך זמן הרצה עצמו. זה גם מאוד נוח לתיעול קוד; במקום לשלב מחרוזות עם הפעולה `+`, אתה מילא תבנית שמשפרת ביצועים ושמירה על קוד נקי וקריא.

מנגד, שים לב: אם אתה לא צריך לחשב ערכים או לשלב ערכים משתנים, לעיתים שימוש במחרוזות בלי interpolation (כלומר עם גרשיים יחידים `'`) יכול להיות מהיר יותר מכיוון שאין צורך בחישובים או הבדלות בזמן ריצה.

## לקרוא גם
- [_Why's (Poignant) Guide to Ruby_: הסברים מעמיקים ויצירתיים (ספר אלקטרוני חופשי)](https://poignant.guide/book/chapter-5.html)
