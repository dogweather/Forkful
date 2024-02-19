---
aliases:
- /he/powershell/manipulating-files-with-cli-one-liners/
date: 2024-01-27 16:21:11.305973-07:00
description: "\u05E9\u05D9\u05E0\u05D5\u05D9 \u05E7\u05D1\u05E6\u05D9\u05DD \u05D1\
  \u05D0\u05DE\u05E6\u05E2\u05D5\u05EA \u05E9\u05D5\u05E8\u05EA \u05E4\u05E7\u05D5\
  \u05D3\u05D4 \u05D7\u05D3-\u05E9\u05D5\u05E8\u05EA\u05D9\u05EA \u05D1-PowerShell\
  \ \u05DE\u05D3\u05D5\u05D1\u05E8 \u05E2\u05DC \u05E9\u05D9\u05E0\u05D5\u05D9, \u05D4\
  \u05E2\u05D1\u05E8\u05D4, \u05D0\u05D5 \u05E7\u05D1\u05DC\u05EA \u05E0\u05EA\u05D5\
  \u05E0\u05D9 \u05E7\u05D1\u05E6\u05D9\u05DD \u05D1\u05D0\u05D5\u05E4\u05DF \u05D9\
  \u05E9\u05D9\u05E8 \u05DE\u05E9\u05D5\u05E8\u05EA \u05D4\u05E4\u05E7\u05D5\u05D3\
  \u05D4. \u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD\
  \ \u05D6\u05D0\u05EA \u05DC\u05E6\u05D5\u05E8\u05DA \u05D9\u05E2\u05D9\u05DC\u05D5\
  \u05EA;\u2026"
lastmod: 2024-02-18 23:08:53.065373
model: gpt-4-0125-preview
summary: "\u05E9\u05D9\u05E0\u05D5\u05D9 \u05E7\u05D1\u05E6\u05D9\u05DD \u05D1\u05D0\
  \u05DE\u05E6\u05E2\u05D5\u05EA \u05E9\u05D5\u05E8\u05EA \u05E4\u05E7\u05D5\u05D3\
  \u05D4 \u05D7\u05D3-\u05E9\u05D5\u05E8\u05EA\u05D9\u05EA \u05D1-PowerShell \u05DE\
  \u05D3\u05D5\u05D1\u05E8 \u05E2\u05DC \u05E9\u05D9\u05E0\u05D5\u05D9, \u05D4\u05E2\
  \u05D1\u05E8\u05D4, \u05D0\u05D5 \u05E7\u05D1\u05DC\u05EA \u05E0\u05EA\u05D5\u05E0\
  \u05D9 \u05E7\u05D1\u05E6\u05D9\u05DD \u05D1\u05D0\u05D5\u05E4\u05DF \u05D9\u05E9\
  \u05D9\u05E8 \u05DE\u05E9\u05D5\u05E8\u05EA \u05D4\u05E4\u05E7\u05D5\u05D3\u05D4\
  . \u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05E2\u05D5\u05E9\u05D9\u05DD \u05D6\
  \u05D0\u05EA \u05DC\u05E6\u05D5\u05E8\u05DA \u05D9\u05E2\u05D9\u05DC\u05D5\u05EA\
  ;\u2026"
title: "\u05DE\u05E0\u05D9\u05E4\u05D5\u05DC\u05E6\u05D9\u05D4 \u05E9\u05DC \u05E7\
  \u05D1\u05E6\u05D9\u05DD \u05D1\u05D0\u05DE\u05E6\u05E2\u05D5\u05EA \u05E9\u05D5\
  \u05E8\u05EA \u05E4\u05E7\u05D5\u05D3\u05D4 \u05D7\u05D3-\u05E9\u05D5\u05E8\u05EA\
  \u05D9\u05EA"
---

{{< edit_this_page >}}

## מה ולמה?

שינוי קבצים באמצעות שורת פקודה חד-שורתית ב-PowerShell מדובר על שינוי, העברה, או קבלת נתוני קבצים באופן ישיר משורת הפקודה. מתכנתים עושים זאת לצורך יעילות; זה מהיר יותר מאשר ניווט בממשקי גרפיים או כתיבת תסריטים ארוכים למשימות פשוטות.

## איך ל:

### קריאת קובץ
כדי להציג במהירות את תוכן של קובץ, השתמשו בפקודה `Get-Content`:
```PowerShell
Get-Content .\example.txt
```

### כתיבה לקובץ
כדי לכתוב משהו חדש לקובץ, ניתן להשתמש ב-`Set-Content`:
```PowerShell
Set-Content -Path .\example.txt -Value "שלום, PowerShell!"
```

### הוספה לקובץ
הוספת נתונים לקצה הקובץ בלי למחוק את תוכנו ניתן לעשות עם `Add-Content`:
```PowerShell
Add-Content -Path .\example.txt -Value "מוסיף את השורה הזאת."
```

### העתקת קבצים
העתקת קובץ היא פשוטה עם `Copy-Item`:
```PowerShell
Copy-Item -Path .\example.txt -Destination .\copy_of_example.txt
```

### מחיקת קבצים
כדי להסיר קובץ, פשוט השתמשו ב-`Remove-Item`:
```PowerShell
Remove-Item -Path .\unwanted_file.txt
```

### חיפוש בתוך קבצים
השתמשו ב-`Select-String` לחיפוש טקסט בתוך קבצים:
```PowerShell
Select-String -Path .\*.txt -Pattern "PowerShell"
```

### שילוב פקודות
PowerShell באמת זוהרת עם היכולת שלה לשרשר פקודות באמצעות צינורות. כך תוכלו למצוא קבצים ולהעתיק אותם לתיקייה חדשה:
```PowerShell
Get-ChildItem -Path .\*.log | Copy-Item -Destination C:\Logs
```

## הבנה עמוקה

היסטורית, PowerShell הוצגה כאלטרנטיבה יותר חזקה לחלון הפקודה המסורתי ב-Windows, והציעה גישה חסרת תקדים לאינטרנלים של המערכת ולמאגרי נתונים. היא משלבת את מהירות שורת הפקודה עם גמישות של תסריט, והופכת אותה לכלי בלתי ניתן להערכה עבור מנהלי מערכת ומפתחים המבוססים על Windows.

אלטרנטיבות ל-PowerShell לשינוי קבצים כוללות כלים מבוססי Unix כמו `sed`, `awk`, `grep`, ותסריט `bash` עבור משתמשי Linux ו-MacOS. למרות שכלים אלו חזקים מאוד ויש להם יתרונות משלהם, PowerShell מציעה אינטגרציה עמוקה עם סביבות Windows.

אספקט מרשים של PowerShell הוא אופייה המונחה-עצמים. בניגוד לשפות תסריט רבות המתייחסות לכל דבר כמו למחרוזות או לזרמים של בתים, PowerShell עובדת ישירות עם אובייקטים של .NET. זה אומר שכאשר אתם מניפולים קבצים, אתם עובדים עם אובייקטים עשירים המספקים מגוון רחב של תכונות ומתודות, שהופך משימות מורכבות לניהוליות יותר.

אחד מחולשות PowerShell, במיוחד עבור משתמשי Linux ו-MacOS, היא המילוליות הנתפסת שלה בהשוואה לתסריטי bash או השימוש בכלים של ממשק שורת פקודה של Unix. בנוסף, האינטגרציה העמוקה של PowerShell עם Windows לעיתים קרובות יכולה להפוך תסריטים רוחביי פלטפורמות למעט יותר מאתגרים, למרות שמאמצי PowerShell Core שואפים לגשר על הפער הזה בצורה יעילה.

ללא קשר לחולשותיה, כוחה של PowerShell טמון ביכולות החד-שורתיות העוצמתיות שלה, סביבת התסריט המשולבת, והגישה המקיפה שהיא מספקת לאקוסיסטם של Windows, הופכת אותה לכלי חיוני עבור אלו המחפשים לשנות קבצים ועוד הרבה יותר, ישירות משורת הפקודה.
