---
title:                "כתיבת קובץ טקסט"
aliases:
- /he/java/writing-a-text-file/
date:                  2024-02-03T19:29:17.590619-07:00
model:                 gpt-4-0125-preview
simple_title:         "כתיבת קובץ טקסט"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/java/writing-a-text-file.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## מה ולמה?

כתיבה לקובץ טקסט בג'אווה היא פעולה שמתבצעת באמצעות שימוש ביכולות של השפה ליצירה וכתיבת תוכן בקבצים על מערכת הקבצים. תכנתים עושים זאת מסיבות שונות, כמו לוגים, יצוא נתונים, או שמירת מצב היישום לשליפה מאוחרת יותר.

## איך לעשות:

### באמצעות `java.nio.file` (ספריית סטנדרט)

החבילה החדשה של I/O של Java (`java.nio.file`) מספקת גישה יותר גמישה לעבודה עם קבצים. הנה דרך פשוטה לכתוב לקובץ באמצעות `Files.write()`:

```java
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.Arrays;
import java.util.List;

public class TextFileWriterNIO {
    public static void main(String[] args) {
        List<String> lines = Arrays.asList("שורה 1", "שורה 2", "שורה 3");
        try {
            Files.write(Paths.get("example.txt"), lines);
            System.out.println("הקובץ נכתב בהצלחה!");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

פלט:

```
הקובץ נכתב בהצלחה!
```

### באמצעות `java.io` (ספריית סטנדרט)

לגישה יותר מסורתית, `java.io.FileWriter` הוא בחירה טובה לכתיבת קבצי טקסט בקלות:

```java
import java.io.FileWriter;
import java.io.IOException;

public class TextFileWriterIO {
    public static void main(String[] args) {
        try (FileWriter writer = new FileWriter("example.txt")) {
            writer.write("שלום, עולם!\n");
            writer.append("זו שורה נוספת.");
            System.out.println("הקובץ נכתב בהצלחה!");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

פלט:

```
הקובץ נכתב בהצלחה!
```

### באמצעות Apache Commons IO

ספריית Apache Commons IO מפשטת הרבה פעולות, כולל כתיבת קבצים. הנה איך לכתוב לקובץ באמצעות `FileUtils.writeStringToFile()`:

ראשית, הוסף את התלות לפרויקט שלך. אם אתה משתמש ב-Maven, כלול:

```xml
<dependency>
  <groupId>org.apache.commons</groupId>
  <artifactId>commons-io</artifactId>
  <version>2.11.0</version> <!-- בדוק את הגרסה האחרונה -->
</dependency>
```

לאחר מכן, השתמש בקוד הבא כדי לכתוב טקסט לקובץ:

```java
import org.apache.commons.io.FileUtils;
import java.io.File;
import java.io.IOException;

public class TextFileWriterCommonsIO {
    public static void main(String[] args) {
        try {
            FileUtils.writeStringToFile(new File("example.txt"), "זה טקסט שנכתב באמצעות Commons IO.", "UTF-8");
            System.out.println("הקובץ נכתב בהצלחה!");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}

```

פלט:

```
הקובץ נכתב בהצלחה!
```
