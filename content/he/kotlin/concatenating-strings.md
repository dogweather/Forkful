---
title:                "שרשור מחרוזות"
date:                  2024-01-20T17:35:42.368943-07:00
model:                 gpt-4-1106-preview
simple_title:         "שרשור מחרוזות"
programming_language: "Kotlin"
category:             "Kotlin"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/kotlin/concatenating-strings.md"
---

{{< edit_this_page >}}

## מה ולמה?
תיחום מחרוזות זה פשוט לשרשר אותן יחד ליצירת מחרוזת אחת ארוכה יותר. זה מה שמתכנתים עושים כשהם רוצים לאחד מידע ממקורות שונים לפורמט אחיד.

## איך לעשות:
```Kotlin
fun main() {
    val hello = "שלום"
    val world = "עולם"
    val concatenated = hello + " " + world + "!"
    println(concatenated) // ידפיס: שלום עולם!
}
```
    
בדוגמה הזו ראינו איך פשוט ניתן לשרשר מחרוזות בקוטלין.

```Kotlin
fun main() {
    val words = listOf("שלום", "עולם", "מתכנתים")
    val sentence = words.joinToString(separator = " ") { it }
    println(sentence) // ידפיס: שלום עולם מתכנתים
}
```
הדוגמה הזו מראה דרך נוספת לשרשר רשימה של מחרוזות בקוטלין.

## ניתוח עמוק
היסטורית, שרשור מחרוזות היה אחד הפעולות הבסיסיות בתכנות, דרך אמתחת שפות קידומות כמו C וJavה. בקוטלין, שרשור נעשה גם עם פלוס `+` וגם עם פונקציות כמו `joinToString`. יש אלטרנטיבות נוספות, כמו string templates להכנסה של משתנים בקלות בתוך מחרוזת: `"$hello $world!"`. שרשור יכול להיות פחות יעיל בכמות גדולה כיוון שמחרוזות בקוטלין הן immutable, ולכן לכל שרשור נוצרת מחרוזת חדשה. למזלנו, קומפיילרים מודרניים כמו של קוטלין, מתאימים את הביצועים בהתאם.

## ראה גם
- [Kotlin Documentation: String templates](https://kotlinlang.org/docs/basic-types.html#string-templates)
- [Optimizing String concatenation in Kotlin Bytecode](https://proandroiddev.com/optimizing-string-concatenation-in-kotlin-bytecode-2be0305b3f7)
