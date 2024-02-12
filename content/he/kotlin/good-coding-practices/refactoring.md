---
title:                "שיפור קוד"
aliases:
- /he/kotlin/refactoring/
date:                  2024-01-26T01:47:05.834651-07:00
model:                 gpt-4-0125-preview
simple_title:         "שיפור קוד"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/kotlin/refactoring.md"
---

{{< edit_this_page >}}

## מה ולמה?
הפקטורינג היא התהליך של שינויים קטנים בקוד קיים כדי לשפר את מבנהו, קריאותו וביצועיו מבלי לשנות את התנהגותו החיצונית. מתכנתים מבצעים הפקטורינג כדי להפוך את הקוד ליותר ניתן לתחזוקה, לפשט את הוספת פיצ'רים חדשים, ולזהות ולתקן באגים בקלות רבה יותר.

## איך לעשות:
הנה קטע קוד בקוטלין המראה ריח קוד נפוץ ואת גרסת ההפקטורינג שלו. אנחנו מתחילים עם חתיכת קוד שעושה יותר מדי:

```kotlin
fun processOrders(orders: List<Order>) {
    for (order in orders) {
        print("Order ID: ${order.id}")
        // חישוב סכום הזמנה
        var total = 0.0
        for (item in order.items) {
            total += item.price
        }
        // החלת הנחה
        if (order.customer.isVIP) {
            total *= 0.9
        }
        print("Total: $total")
        // עיבוד נוסף...
    }
}
```

הפקטורינג לקריאות והפרדת דאגות טובה יותר:

```kotlin
fun printOrderSummary(order: Order) {
    print("Order ID: ${order.id}")
    val total = calculateTotal(order)
    print("Total: $total")
}

fun calculateTotal(order: Order): Double {
    var total = order.items.sumOf { it.price }
    return if (order.customer.isVIP) total * 0.9 else total
}

fun processOrders(orders: List<Order>) {
    orders.forEach { printOrderSummary(it) }
}
```

כאן אין פלט לדוגמה מכיוון שלא שינינו את הפונקציונליות, אך קריאות הקוד וניתנותו לתחזוקה קיבלו תמריץ עצום!

## צלילה עמוקה
הפקטורינג כמושג קיים כל עוד תכנות התקיים, אך זכה לתעופה כמשמעות בשנות ה-90, במיוחד לאחר שמרטין פאולר פרסם את "Refactoring: Improving the Design of Existing Code" ב-1999. הספר הזה נתן שם לתרגול והגדיר שיטה מאורגנת להחלתו, כולל קטלוג של טכניקות הפקטורינג.

השוואה בין הפקטורינג לאלטרנטיבות: אפשר לכתוב מחדש קוד מאפס (מסוכן ולוקח זמן), או לבצע שינויים תוספתיים (מוביל לנפיחות תוכנה וחוב טכנולוגי פוטנציאלי). הפקטורינג מצליח להכות בנקודה המתוקה - הוא מעדכן ונקה תוך שמירה על סיכון נמוך.

מבחינת יישום, חשוב להחזיק בסט חזק של טסטים לפני שמתחילים בהפקטורינג כדי להבטיח שלא משנים בטעות את התנהגות התוכנית. רבים מסביבות הפיתוח המודרניות (כולל IntelliJ עבור קוטלין) מציעות כלים אוטומטיים להפקטורינג כמו שינוי שמות משתנים, חילוץ שיטות, ועוד, אשר יכולים להאיץ את התהליך ולצמצם שגיאות.

## ראה גם
- "Refactoring: Improving the Design of Existing Code" מאת מרטין פאולר (עבור העבודה המכוננת על נושא זה)
- מסמכי קוטלין על קונבנציות קידוד: [https://kotlinlang.org/docs/coding-conventions.html](https://kotlinlang.org/docs/coding-conventions.html) (כדי להבין את "הדרך של קוטלין" לקוד נקי)
- תמיכה של JetBrains בהפקטורינג ב-IntelliJ IDEA: [https://www.jetbrains.com/help/idea/refactoring-source-code.html](https://www.jetbrains.com/help/idea/refactoring-source-code.html) (לשימוש מעשי בכלים להפקטורינג)
- המדריך של גוגל להפקטורינג בקנה מידה גדול: [https://testing.googleblog.com/2017/06/code-health-to-comment-or-not-to-comment.html](https://testing.googleblog.com/2017/06/code-health-to-comment-or-not-to-comment.html) (לתובנות על אתגרי הפקטורינג גדולים יותר)
