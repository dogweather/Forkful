---
title:                "עבודה עם TOML"
date:                  2024-01-26T04:21:58.662844-07:00
model:                 gpt-4-0125-preview
simple_title:         "עבודה עם TOML"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/fish-shell/working-with-toml.md"
---

{{< edit_this_page >}}

## מה ולמה?
TOML הוא פורמט קובץ הגדרות, קל לקריאה ולכתיבה עבור בני אדם, וקל לניתוח וייצור עבור מכונות. מתכנתים עובדים עם TOML עבור קבצי הגדרות ברורים והיררכים בפרויקטים שבהם נגישות הקריאה חשובה.

## איך ל:
לקרוא ולעבד TOML ב-Fish, אפשר להשתמש בכלי כמו `yj`, שיכול להמיר TOML ל-JSON. הנה איך:

```fish
# התקנת yj דרך Fisher
fisher install jorgebucaran/yj

# המרת TOML ל-JSON
echo 'title = "TOML Example"' | yj -tj

# פלט לדוגמא
{"title":"TOML Example"}
```

לכתוב TOML, פשוט מבצעים את התהליך ההפוך:

```fish
# המרת JSON ל-TOML
echo '{"title":"JSON Example"}' | yj -jt

# פלט לדוגמא
title = "JSON Example"
```

לעבודות כבדות, שקלו שימוש בכלי CLI מוקדש ל-TOML כמו `toml-cli`.

```fish
# התקנת toml-cli
pip install toml-cli

# הגדרת ערך בקובץ TOML
toml set pyproject.toml tool.poetry.version "1.1.4"

# קבלת ערך מקובץ TOML
set version (toml get pyproject.toml tool.poetry.version)
echo $version
```

## צלילה עמוקה
TOML (Tom's Obvious, Minimal Language), שהוצג על ידי Tom Preston-Werner ב-2013, דומה ל-INI אבל עם מפרט מוגדר והיררכיית נתונים. JSON ו-YAML הם החלופות העיקריות, אך יש להם מסחר ומנה: JSON אינו ידידותי כלפי המשתמש כמו TOML, בעוד ש-YAML יותר מורכב. עיצוב TOML מצליח בסיטואציות שבהן קבצי הגדרות נתונים לעיתים קרובות לטיפול ידני, מאזן בין פשטות לבין ביטוייות. מבחינת יישום, פרשני TOML זמינים עבור רוב שפות התכנות, כולל TomlBombadil עבור Fish שיכול להשתלב ישירות בתסריטים שלכם.

## ראו גם
- המפרט הרשמי של TOML: https://toml.io
- `yj`, כלי להמרה בין TOML, JSON, YAML, ו-XML: https://github.com/jorgebucaran/yj
- `toml-cli`, כלי שורת פקודה עבור TOML: https://github.com/sdispater/toml-cli
