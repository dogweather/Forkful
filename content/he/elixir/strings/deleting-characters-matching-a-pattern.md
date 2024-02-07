---
title:                "מחיקת תווים התואמים לתבנית"
date:                  2024-01-20T17:42:21.030061-07:00
model:                 gpt-4-1106-preview
simple_title:         "מחיקת תווים התואמים לתבנית"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/elixir/deleting-characters-matching-a-pattern.md"
---

{{< edit_this_page >}}

## מה ולמה?
מחיקת תווים שתואמים תבנית היא פעולה שבה אנו מסירים תווים ממחרוזת על פי כלל מסוים. תכנתים עושים את זה בדרך כלל כדי לנקות נתונים, לפרמט מחרוזות לתצורה מסוימת, או להוריד מידע לא רלוונטי.

## איך לעשות:
```elixir
# תחילית פשוטה להסרת כל הספרות ממחרוזת.
String.replace("אני חי בשנת 2023", ~r/\d+/, "")
# Output: "אני חי בשנת "

# להסרת תווים מיוחדים להשאר רק עם אותיות ורווחים.
String.replace("היי! איך הולך? :)", ~r/[^א-ת ]/, "")
# Output: "היי איך הולך "

# הסרת כל רווחי התחילית והסוף.
String.trim("   זה בדיקה    ")
# Output: "זה בדיקה"
```

## צלילה עמוקה
מחיקת תווים תואמים לתבנית היא חלק מטיפול בביטויים רגולריים (Regular Expressions), שהחלו להופיע בשנות ה-50 של המאה ה-20. באליקסיר, אנו משתמשים במודול String ובפונקציות כמו `replace/3` ו-`trim/1` כדי לממש את המחיקה הזו בצורה קלה וגמישה. אלטרנטיבות כוללות תכנתים מובנים אחרים כמו `strip/1` ו-`slice/2` או שימוש במניפולציה ידנית של רשימת התווים באמצעות רקורסיה או איטראציה.

## ראה גם
- [Elixir's String Module](https://hexdocs.pm/elixir/String.html)
- [Regular Expressions in Elixir](https://hexdocs.pm/elixir/Regex.html)
- [Programming Elixir ≥ 1.6 book by Dave Thomas](http://pragprog.com/book/elixir16/programming-elixir-1-6)
