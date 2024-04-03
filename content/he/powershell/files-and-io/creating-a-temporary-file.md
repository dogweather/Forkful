---
date: 2024-01-20 17:41:15.415309-07:00
description: "\u05D9\u05E6\u05D9\u05E8\u05EA \u05E7\u05D5\u05D1\u05E5 \u05D6\u05DE\
  \u05E0\u05D9 \u05D4\u05D9\u05D0 \u05EA\u05D4\u05DC\u05D9\u05DA \u05E9\u05D1\u05D5\
  \ \u05D0\u05E0\u05D5 \u05DE\u05D9\u05D9\u05E6\u05E8\u05D9\u05DD \u05E7\u05D5\u05D1\
  \u05E5 \u05E9\u05DE\u05D9\u05D5\u05E2\u05D3 \u05DC\u05E9\u05D9\u05DE\u05D5\u05E9\
  \ \u05D7\u05D3-\u05E4\u05E2\u05DE\u05D9 \u05D0\u05D5 \u05E7\u05E6\u05E8-\u05D8\u05D5\
  \u05D5\u05D7. \u05EA\u05DB\u05E0\u05D9\u05EA\u05E0\u05D9\u05DD \u05E2\u05D5\u05E9\
  \u05D9\u05DD \u05D6\u05D0\u05EA \u05DB\u05D3\u05D9 \u05DC\u05D0\u05D7\u05E1\u05DF\
  \ \u05DE\u05D9\u05D3\u05E2 \u05D6\u05DE\u05E0\u05D9, \u05DB\u05D2\u05D5\u05DF \u05E0\
  \u05EA\u05D5\u05E0\u05D9\u05DD \u05DC\u05E4\u05E0\u05D9 \u05E2\u05D9\u05D1\u05D5\
  \u05D3, \u05D0\u05D5 \u05DB\u05D7\u05DC\u05E7\u2026"
lastmod: '2024-03-13T22:44:39.730423-06:00'
model: gpt-4-1106-preview
summary: "\u05D9\u05E6\u05D9\u05E8\u05EA \u05E7\u05D5\u05D1\u05E5 \u05D6\u05DE\u05E0\
  \u05D9 \u05D4\u05D9\u05D0 \u05EA\u05D4\u05DC\u05D9\u05DA \u05E9\u05D1\u05D5 \u05D0\
  \u05E0\u05D5 \u05DE\u05D9\u05D9\u05E6\u05E8\u05D9\u05DD \u05E7\u05D5\u05D1\u05E5\
  \ \u05E9\u05DE\u05D9\u05D5\u05E2\u05D3 \u05DC\u05E9\u05D9\u05DE\u05D5\u05E9 \u05D7\
  \u05D3-\u05E4\u05E2\u05DE\u05D9 \u05D0\u05D5 \u05E7\u05E6\u05E8-\u05D8\u05D5\u05D5\
  \u05D7."
title: "\u05D9\u05E6\u05D9\u05E8\u05EA \u05E7\u05D5\u05D1\u05E5 \u05D6\u05DE\u05E0\
  \u05D9"
weight: 21
---

## איך לעשות:
כדי ליצור קובץ זמני ב-PowerShell, ניתן להשתמש בפונקציה `New-TemporaryFile`:

```PowerShell
# יצירת קובץ זמני
$tempFile = New-TemporaryFile
# הדפסת שם הקובץ
Write-Host "Temporary file created: $($tempFile.FullName)"
```

תוצאת דוגמה:
```
Temporary file created: C:\Users\<UserName>\AppData\Local\Temp\tmpA1B2.tmp
```

## צלילה לעומק:
בעבר, יצירת קובץ זמני נעשתה על ידי קביעת שם קובץ באופן ידני ושמירת קובץ עם סיומת זמנית. הפונקציה `New-TemporaryFile` מיושמת מאז PowerShell 5.0 ומקלה על התהליך על ידי אוטומציה. ישנן אלטרנטיבות כמו שימוש ב-[System.IO.Path]::GetTempFileName() המובנית של .NET ב-PowerShell:

```PowerShell
# אלטרנטיבה ליצירת קובץ זמני עם .NET
$tempFileName = [System.IO.Path]::GetTempFileName()
Write-Host "Temporary file created: $tempFileName"
```

זכרו, קבצים זמניים נועדו להימחק אחרי שימוש. אם לא תנקו אותם, הם יכולים לצבור ולכבד את המערכת.

## גם כדאי לראות:
- [מדריך לפונקציה New-TemporaryFile](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/new-temporaryfile?view=powershell-7)
