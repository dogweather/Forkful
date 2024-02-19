---
aliases:
- /he/java/logging/
date: 2024-01-26 01:06:52.424048-07:00
description: "\u05DC\u05D5\u05D2\u05D9\u05E0\u05D2 \u05D4\u05D5\u05D0 \u05DC\u05DE\
  \u05E2\u05E9\u05D4 \u05D4\u05EA\u05D4\u05DC\u05D9\u05DA \u05E9\u05DC \u05EA\u05D9\
  \u05E2\u05D5\u05D3 \u05D0\u05D9\u05E8\u05D5\u05E2\u05D9\u05DD \u05D4\u05DE\u05EA\
  \u05E8\u05D7\u05E9\u05D9\u05DD \u05D1\u05EA\u05D5\u05DA \u05D0\u05E4\u05DC\u05D9\
  \u05E7\u05E6\u05D9\u05D9\u05EA \u05EA\u05D5\u05DB\u05E0\u05D4. \u05DE\u05EA\u05DB\
  \u05E0\u05EA\u05D9\u05DD \u05DE\u05EA\u05E2\u05D3\u05D9\u05DD \u05D0\u05D9\u05E8\
  \u05D5\u05E2\u05D9\u05DD \u05D0\u05DC\u05D4 \u05DB\u05D3\u05D9 \u05DC\u05EA\u05E4\
  \u05D5\u05E1 \u05DE\u05D9\u05D3\u05E2 \u05D1\u05D6\u05DE\u05DF \u05E8\u05D9\u05E6\
  \u05D4, \u05DC\u05D0\u05D1\u05D7\u05DF \u05D1\u05E2\u05D9\u05D5\u05EA, \u05DC\u05E4\
  \u05E7\u05D7 \u05E2\u05DC \u05D4\u05EA\u05E0\u05D4\u05D2\u05D5\u05EA\u2026"
lastmod: 2024-02-18 23:08:52.715466
model: gpt-4-1106-preview
summary: "\u05DC\u05D5\u05D2\u05D9\u05E0\u05D2 \u05D4\u05D5\u05D0 \u05DC\u05DE\u05E2\
  \u05E9\u05D4 \u05D4\u05EA\u05D4\u05DC\u05D9\u05DA \u05E9\u05DC \u05EA\u05D9\u05E2\
  \u05D5\u05D3 \u05D0\u05D9\u05E8\u05D5\u05E2\u05D9\u05DD \u05D4\u05DE\u05EA\u05E8\
  \u05D7\u05E9\u05D9\u05DD \u05D1\u05EA\u05D5\u05DA \u05D0\u05E4\u05DC\u05D9\u05E7\
  \u05E6\u05D9\u05D9\u05EA \u05EA\u05D5\u05DB\u05E0\u05D4. \u05DE\u05EA\u05DB\u05E0\
  \u05EA\u05D9\u05DD \u05DE\u05EA\u05E2\u05D3\u05D9\u05DD \u05D0\u05D9\u05E8\u05D5\
  \u05E2\u05D9\u05DD \u05D0\u05DC\u05D4 \u05DB\u05D3\u05D9 \u05DC\u05EA\u05E4\u05D5\
  \u05E1 \u05DE\u05D9\u05D3\u05E2 \u05D1\u05D6\u05DE\u05DF \u05E8\u05D9\u05E6\u05D4\
  , \u05DC\u05D0\u05D1\u05D7\u05DF \u05D1\u05E2\u05D9\u05D5\u05EA, \u05DC\u05E4\u05E7\
  \u05D7 \u05E2\u05DC \u05D4\u05EA\u05E0\u05D4\u05D2\u05D5\u05EA\u2026"
title: "\u05E8\u05D9\u05E9\u05D5\u05DD \u05E4\u05E2\u05D5\u05DC\u05D5\u05EA (\u05DC\
  \u05D5\u05D2\u05D9\u05DD)"
---

{{< edit_this_page >}}

## מה ולמה?
לוגינג הוא למעשה התהליך של תיעוד אירועים המתרחשים בתוך אפליקציית תוכנה. מתכנתים מתעדים אירועים אלה כדי לתפוס מידע בזמן ריצה, לאבחן בעיות, לפקח על התנהגות המערכת, וליצור מסלול ביקורת עבור מטרות אבטחה והתאמה לתקנים.

## כיצד לעשות זאת:
הנה דרך פשוטה להתחיל עם לוגינג ב-Java באמצעות החבילה המובנית `java.util.logging`.

```java
import java.util.logging.Logger;
import java.util.logging.Level;

public class AppLogging {
    private final static Logger LOGGER = Logger.getLogger(Logger.GLOBAL_LOGGER_NAME);

    public static void main(String[] args) {
        LOGGER.info("Logging an INFO-level message");

        try {
            int division = 10 / 0;
        } catch (ArithmeticException e) {
            LOGGER.log(Level.SEVERE, "אירעה חריגה", e);
        }
    }
}
```

זה יפיק פלט בסגנון הבא:

```
יול 03, 2023 2:00:00 PM AppLogging main
INFO: תיעוד הודעה ברמת INFO
יול 03, 2023 2:00:00 PM AppLogging main
SEVERE: אירעה חריגה
java.lang.ArithmeticException: / by zero
    at AppLogging.main(AppLogging.java:10)
```

## עיון מעמיק
לוגינג ב-Java התפתח לאורך השנים. בעבר, לוגינג היה דבר יותר חד-פעמי עם פלטים של המערכת ומנגנונים שנכתבו באופן עצמאי. למרות זאת, הצורך בתקנון הביא לידי היווצרות של ממשקי תכנות ללוגינג כמו `Log4j` ו-`SLF4J`. החבילה `java.util.logging` הוצגה ב-JDK 1.4, ומספקת דרך מתוקננת לתעד הודעות.

אלטרנטיבות ל-`java.util.logging` (JUL) כוללות את Log4j 2 ו-SLF4J. למרות ש-JUL מובנית ב-Java ולכן אינה דורשת תלויות נוספות, Log4j 2 ו-SLF4J מציעים תכונות מתקדמות יותר כמו שליטה דקה יותר על תצורת הלוגינג, לוגינג אסינכרוני, וביצועים טובים יותר.

מבחינת היישום, לוגינג יכול להיות סינכרוני, שבו כל הודעת לוג מעובדת באשך שיצר אותה, או אסינכרוני, שבו ההודעות מועברות לאשך נפרד. לוגינג אסינכרוני יכול לשפר ביצועים אך מצריך התמודדות עם סיבוכיות של ריבוי משימות והבטחה שהודעות לוג לא יאבדו במקרה של קריסת האפליקציה.

## ראה גם
- [Log4j 2](https://logging.apache.org/log4j/2.x/)
- [SLF4J](http://www.slf4j.org/)
- [סקירה רשמית של אורקל על לוגינג](https://docs.oracle.com/javase/8/docs/technotes/guides/logging/overview.html)
- [מדריך על java.util.logging](https://www.vogella.com/tutorials/Logging/article.html)
