---
aliases:
- /he/python/writing-tests/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:32:01.143678-07:00
description: "\u05DB\u05EA\u05D9\u05D1\u05EA \u05D1\u05D3\u05D9\u05E7\u05D5\u05EA\
  \ \u05D1-Python \u05DB\u05D5\u05DC\u05DC\u05EA \u05D9\u05E6\u05D9\u05E8\u05EA \u05E1\
  \u05E7\u05E8\u05D9\u05E4\u05D8\u05D9\u05DD \u05D0\u05D5\u05D8\u05D5\u05DE\u05D8\u05D9\
  \u05D9\u05DD \u05DC\u05D0\u05D9\u05DE\u05D5\u05EA \u05E0\u05DB\u05D5\u05E0\u05D5\
  \u05EA \u05D4\u05E7\u05D5\u05D3 \u05E9\u05DC\u05DA. \u05DE\u05EA\u05DB\u05E0\u05EA\
  \u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9\
  \ \u05DC\u05D5\u05D5\u05D3\u05D0 \u05E9\u05D4\u05E4\u05D5\u05E0\u05E7\u05E6\u05D9\
  \u05D5\u05EA \u05D0\u05D5 \u05D4\u05DE\u05D7\u05DC\u05E7\u05D5\u05EA \u05E9\u05DC\
  \u05D4\u05DD \u05E4\u05D5\u05E2\u05DC\u05D5\u05EA \u05DB\u05E6\u05E4\u05D5\u05D9\
  \ \u05EA\u05D7\u05EA \u05EA\u05E0\u05D0\u05D9\u05DD\u2026"
lastmod: 2024-02-18 23:08:52.440348
model: gpt-4-0125-preview
summary: "\u05DB\u05EA\u05D9\u05D1\u05EA \u05D1\u05D3\u05D9\u05E7\u05D5\u05EA \u05D1\
  -Python \u05DB\u05D5\u05DC\u05DC\u05EA \u05D9\u05E6\u05D9\u05E8\u05EA \u05E1\u05E7\
  \u05E8\u05D9\u05E4\u05D8\u05D9\u05DD \u05D0\u05D5\u05D8\u05D5\u05DE\u05D8\u05D9\u05D9\
  \u05DD \u05DC\u05D0\u05D9\u05DE\u05D5\u05EA \u05E0\u05DB\u05D5\u05E0\u05D5\u05EA\
  \ \u05D4\u05E7\u05D5\u05D3 \u05E9\u05DC\u05DA. \u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\
  \u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9 \u05DC\
  \u05D5\u05D5\u05D3\u05D0 \u05E9\u05D4\u05E4\u05D5\u05E0\u05E7\u05E6\u05D9\u05D5\u05EA\
  \ \u05D0\u05D5 \u05D4\u05DE\u05D7\u05DC\u05E7\u05D5\u05EA \u05E9\u05DC\u05D4\u05DD\
  \ \u05E4\u05D5\u05E2\u05DC\u05D5\u05EA \u05DB\u05E6\u05E4\u05D5\u05D9 \u05EA\u05D7\
  \u05EA \u05EA\u05E0\u05D0\u05D9\u05DD\u2026"
title: "\u05DB\u05EA\u05D9\u05D1\u05EA \u05D1\u05D3\u05D9\u05E7\u05D5\u05EA"
---

{{< edit_this_page >}}

## מה ולמה?
כתיבת בדיקות ב-Python כוללת יצירת סקריפטים אוטומטיים לאימות נכונות הקוד שלך. מתכנתים עושים זאת כדי לוודא שהפונקציות או המחלקות שלהם פועלות כצפוי תחת תנאים שונים, מה שעוזר לזהות טעויות מוקדם ומקל על תחזוקה ושיפוץ קוד.

## איך לעשות את זה:
Python מגיעה עם מודול מובנה לכתיבת בדיקות בשם `unittest`. זו הדרך שבה אתה יכול להשתמש בה כדי לבדוק פונקציה פשוטה:

```python
import unittest

def add(a, b):
    return a + b

class TestAddFunction(unittest.TestCase):
    def test_add(self):
        self.assertEqual(add(1, 2), 3)
        self.assertEqual(add(-1, 1), 0)
        self.assertNotEqual(add(10, 2), 12, "אמור להיות 12")

if __name__ == '__main__':
    unittest.main()
```

כשתריץ את סקריפט הבדיקה הזה, אתה אמור לראות פלט שמציין שהבדיקות שלך עברו (או נכשלו).

לבדיקות יותר מודרניות ומובעות, אתה יכול להשתמש בספרייה צד שלישי כמו `pytest`. ראשית, תצטרך להתקין את זה באמצעות pip:

```shell
pip install pytest
```

לאחר מכן, אתה יכול לכתוב את הבדיקות שלך בדרך פשוטה יותר ללא הצורך לירש מתת-מחלקה כלשהי:

```python
# שמור את זה בקובץ בשם test_with_pytest.py
def add(a, b):
    return a + b

def test_add():
    assert add(1, 2) == 3
    assert add(-1, 1) == 0
    assert add(10, 2) != 12, "אמור להיות 12"
```

כדי להריץ את הבדיקות שלך עם `pytest`, פשוט בצע:

```shell
pytest test_with_pytest.py
```

אתה אמור לראות פלט מ-pytest המראה את תוצאות הבדיקות שלך.
