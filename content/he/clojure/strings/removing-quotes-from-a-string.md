---
date: 2024-01-26 03:42:05.328840-07:00
description: "\u05DC\u05D4\u05E1\u05D9\u05E8 \u05DE\u05E8\u05DB\u05D0\u05D5\u05EA\
  \ \u05DE\u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05E4\u05D9\u05E8\u05D5\u05E9\u05D5\
  \ \u05DC\u05D4\u05D9\u05E4\u05D8\u05E8 \u05DE\u05EA\u05D5\u05D5\u05D9 \u05D4\u05E6\
  \u05D9\u05D8\u05D5\u05D8 \u05D4\u05DB\u05E4\u05D5\u05DC\u05D9\u05DD \u05D0\u05D5\
  \ \u05D4\u05D9\u05D7\u05D9\u05D3\u05D9\u05DD \u05D4\u05DE\u05E7\u05D9\u05E4\u05D9\
  \u05DD \u05D0\u05EA \u05D4\u05D8\u05E7\u05E1\u05D8 \u05E9\u05DC\u05DA. \u05DE\u05EA\
  \u05DB\u05E0\u05EA\u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\u05D0\u05EA\
  \ \u05DB\u05D3\u05D9 \u05DC\u05E0\u05E7\u05D5\u05EA \u05E0\u05EA\u05D5\u05E0\u05D9\
  \u05DD, \u05DC\u05D4\u05D1\u05D8\u05D9\u05D7 \u05D0\u05D7\u05D9\u05D3\u05D5\u05EA\
  , \u05D0\u05D5 \u05DC\u05D4\u05DB\u05D9\u05DF\u2026"
lastmod: '2024-03-13T22:44:38.684858-06:00'
model: gpt-4-0125-preview
summary: "\u05DC\u05D4\u05E1\u05D9\u05E8 \u05DE\u05E8\u05DB\u05D0\u05D5\u05EA \u05DE\
  \u05DE\u05D7\u05E8\u05D5\u05D6\u05EA \u05E4\u05D9\u05E8\u05D5\u05E9\u05D5 \u05DC\
  \u05D4\u05D9\u05E4\u05D8\u05E8 \u05DE\u05EA\u05D5\u05D5\u05D9 \u05D4\u05E6\u05D9\
  \u05D8\u05D5\u05D8 \u05D4\u05DB\u05E4\u05D5\u05DC\u05D9\u05DD \u05D0\u05D5 \u05D4\
  \u05D9\u05D7\u05D9\u05D3\u05D9\u05DD \u05D4\u05DE\u05E7\u05D9\u05E4\u05D9\u05DD\
  \ \u05D0\u05EA \u05D4\u05D8\u05E7\u05E1\u05D8 \u05E9\u05DC\u05DA."
title: "\u05D4\u05E1\u05E8\u05EA \u05DE\u05E8\u05DB\u05D0\u05D5\u05EA \u05DE\u05DE\
  \u05D7\u05E8\u05D5\u05D6\u05EA"
weight: 9
---

## איך לעשות:
ב-Clojure, מחרוזות הן בלתי שינויות, אז כשאנחנו מדברים על "להסיר מרכאות", אנו למעשה מדברים על יצירת מחרוזת חדשה ללא מרכאות. הנה הדרך באמצעות `clojure.string/replace`:

```clojure
(require '[clojure.string :as str])

; בואו ניפטר מהמרכאות הכפולות
(defn remove-double-quotes [s]
  (str/replace s #"\"" ""))

; ונגרש את המרכאות היחידות
(defn remove-single-quotes [s]
  (str/replace s #"\'" ""))

; שימוש לדוגמה:
(remove-double-quotes "\"שלום, עולם!\"") ; => "שלום, עולם!"
(remove-single-quotes "'שלום, עולם!'")   ; => "שלום, עולם!"
```
רוצה לטפל הן במרכאות הכפולות והן ביחידות במכה אחת? תראו את זה:

```clojure
(defn remove-quotes [s]
  (str/replace s #"[\"\']" ""))

; שימוש לדוגמה:
(remove-quotes "\"שלום, 'Clojure' עולם!\"") ; => "שלום, Clojure עולם!"
```

## צלילה לעומק
בימי קדם, כשהנתונים היו בולטאניים יותר מחדרו של ילד, מרכאות במחרוזות היו הנורמה לציון טקסט. אבל ככל שמדעי המחשב התפתחו, מרכאות הפכו ליותר מסתם סימני הפרדת טקסט - הן קיבלו תפקידים תחביריים בשפות תכנות.

Clojure, עם המורשת ה-Lisp שלה, אינה משתמשת במרכאות באותה הדרך שבה ייתכן ששפות אחרות עושות. בוודאי שהן משמשות לציון מחרוזות, אבל להן גם יש תפקיד מיוחד ביצירת ליטרלים. בכל מקרה, הסרת מרכאות ממחרוזות נותרה משימה לאורך הזמן.

למה שלא פשוט נחתוך את קצוות המחרוזת? ובכן, זה מניח שהמרכאות שלך תמיד מחובקות את ההתחלה והסוף של המחרוזת שלך כמו זוג סבים אוהבים יתר על המידה. נתונים בעולם האמיתי הם מורכבים יותר. כאן נכנסים ביטויים רגולריים (regular expressions), שמאפשרים לך לזהות את המרכאות בלי תלות במיקום שלהם.

אלטרנטיבות? בטח, אתה יכול להתחכם עם `subs`, `trim`, `triml`, `trimr`, או אפילו טרנסדוסרים אם אתה רוצה להרשים. אבל `replace` עם ביטויים רגולריים זה כמו להביא חרב לייזר לקרב סכינים - זה פותר את הבעיה בדיוק.

## ראה גם
אם המוח שלך גודל לעוד נפלאות של טיפול במחרוזות ב-Clojure, הפירורי לחם האלה עשויים לעזור:

- ClojureDocs על `clojure.string/replace`: https://clojuredocs.org/clojure.string/replace
- ביטויים רגולריים ב-Clojure: https://clojure.org/guides/learn/syntax#_regex
- התממשקות עם Java לטיפול במחרוזות (Clojure רצה על JVM לבסוף): https://clojure.org/reference/java_interop#_working_with_strings

אל תעצור רק בהסרת מרכאות. יש עולם שלם של כישופי מחרוזות שם בארץ Clojure בהמתנה להתגלות.
