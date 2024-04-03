---
date: 2024-01-20 17:58:23.923309-07:00
description: "\u05D7\u05D9\u05E4\u05D5\u05E9 \u05D5\u05D4\u05D7\u05DC\u05E4\u05D4\
  \ \u05E9\u05DC \u05D8\u05E7\u05E1\u05D8 \u05D4\u05D5\u05D0 \u05E4\u05E2\u05D5\u05DC\
  \u05D4 \u05D1\u05E1\u05D9\u05E1\u05D9\u05EA \u05D1\u05EA\u05DB\u05E0\u05D5\u05EA\
  \ \u05E9\u05D1\u05D4 \u05D0\u05E0\u05D5 \u05DE\u05D5\u05E6\u05D0\u05D9\u05DD \u05DE\
  \u05D7\u05E8\u05D5\u05D6\u05EA \u05DE\u05E1\u05D5\u05D9\u05DE\u05EA \u05D5\u05DE\
  \u05D7\u05DC\u05D9\u05E4\u05D9\u05DD \u05D0\u05D5\u05EA\u05D4 \u05D1\u05D0\u05D7\
  \u05E8\u05EA. \u05EA\u05DB\u05E0\u05D9\u05EA\u05E0\u05D9\u05DD \u05E2\u05D5\u05E9\
  \u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9 \u05DC\u05E2\u05D3\u05DB\u05DF\
  \ \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD, \u05DC\u05EA\u05E7\u05DF \u05E9\u05D2\u05D9\
  \u05D0\u05D5\u05EA \u05D0\u05D5 \u05DC\u05DE\u05D8\u05E8\u05D5\u05EA\u2026"
lastmod: '2024-03-13T22:44:39.106067-06:00'
model: gpt-4-1106-preview
summary: "\u05D7\u05D9\u05E4\u05D5\u05E9 \u05D5\u05D4\u05D7\u05DC\u05E4\u05D4 \u05E9\
  \u05DC \u05D8\u05E7\u05E1\u05D8 \u05D4\u05D5\u05D0 \u05E4\u05E2\u05D5\u05DC\u05D4\
  \ \u05D1\u05E1\u05D9\u05E1\u05D9\u05EA \u05D1\u05EA\u05DB\u05E0\u05D5\u05EA \u05E9\
  \u05D1\u05D4 \u05D0\u05E0\u05D5 \u05DE\u05D5\u05E6\u05D0\u05D9\u05DD \u05DE\u05D7\
  \u05E8\u05D5\u05D6\u05EA \u05DE\u05E1\u05D5\u05D9\u05DE\u05EA \u05D5\u05DE\u05D7\
  \u05DC\u05D9\u05E4\u05D9\u05DD \u05D0\u05D5\u05EA\u05D4 \u05D1\u05D0\u05D7\u05E8\
  \u05EA."
title: "\u05D7\u05D9\u05E4\u05D5\u05E9 \u05D5\u05D4\u05D7\u05DC\u05E4\u05EA \u05D8\
  \u05E7\u05E1\u05D8"
weight: 10
---

## איך לעשות:
```Java
public class StringReplace {
    public static void main(String[] args) {
        String originalText = "תכנות זה מהנה! לתכנת ב-Java זה עוד יותר מהנה!";
        String searchText = "מהנה";
        String replacementText = "מעולה";

        String replacedText = originalText.replaceAll(searchText, replacementText);

        System.out.println(replacedText);
    }
}
```
פלט:
```
תכנות זה מעולה! לתכנת ב-Java זה עוד יותר מעולה!
```

## צלילה לעומק:
חיפוש והחלפה של טקסט הוא מושג שנולד בימים של עריכת טקסט אינטראקטיבית בשנות ה-60. ב-Java, השינוי טקטסט כולל שיטות כמו `replace()`, `replaceAll()`, ו-`replaceFirst()`. זהירות עם `replaceAll()` - היא משתמשת בפקודות ביטוי רגולרי, וזה יכול להיות קצת מפתיע. כתחליף, ישנן ספריות צד שלישי כמו Apache Commons Lang המקלות על החלפת טקסט עם ממשק ידידותי יותר.

## ראה גם:
- [Java String replaceAll() Method](https://www.javatpoint.com/java-string-replaceall)
- [Oracle JavaDocs - String](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/String.html)
- [Apache Commons Lang StringUtils](https://commons.apache.org/proper/commons-lang/javadocs/api-release/org/apache/commons/lang3/StringUtils.html)
