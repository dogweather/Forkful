---
changelog:
- 2024-01-30, gpt-4-0125-preview, translated from English
date: 2024-01-30 19:13:25.739779-07:00
description: "\u05DE\u05E2\u05E8\u05DB\u05D9\u05DD \u05D0\u05E1\u05D5\u05E6\u05D9\u05D0\
  \u05D8\u05D9\u05D1\u05D9\u05D9\u05DD, \u05D4\u05D9\u05D3\u05D5\u05E2\u05D9\u05DD\
  \ \u05D2\u05DD \u05DB\u05D8\u05D1\u05DC\u05D0\u05D5\u05EA \u05D2\u05D9\u05D1\u05D5\
  \u05D1 \u05D0\u05D5 \u05DE\u05D9\u05DC\u05D5\u05E0\u05D9\u05DD \u05D1-PowerShell,\
  \ \u05DE\u05D0\u05E4\u05E9\u05E8\u05D9\u05DD \u05DC\u05DA \u05DC\u05D0\u05D7\u05E1\
  \u05DF \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD \u05D1\u05D6\u05D5\u05D2\u05D5\u05EA\
  \ \u05DE\u05E4\u05EA\u05D7-\u05E2\u05E8\u05DA, \u05DE\u05D4 \u05E9\u05D4\u05D5\u05E4\
  \u05DA \u05D0\u05EA \u05D0\u05D7\u05D6\u05D5\u05E8 \u05D4\u05E0\u05EA\u05D5\u05E0\
  \u05D9\u05DD \u05DC\u05E4\u05E9\u05D5\u05D8 \u05D5\u05D9\u05E2\u05D9\u05DC.\u2026"
lastmod: '2024-03-13T22:44:39.683436-06:00'
model: gpt-4-0125-preview
summary: "\u05DE\u05E2\u05E8\u05DB\u05D9\u05DD \u05D0\u05E1\u05D5\u05E6\u05D9\u05D0\
  \u05D8\u05D9\u05D1\u05D9\u05D9\u05DD, \u05D4\u05D9\u05D3\u05D5\u05E2\u05D9\u05DD\
  \ \u05D2\u05DD \u05DB\u05D8\u05D1\u05DC\u05D0\u05D5\u05EA \u05D2\u05D9\u05D1\u05D5\
  \u05D1 \u05D0\u05D5 \u05DE\u05D9\u05DC\u05D5\u05E0\u05D9\u05DD \u05D1-PowerShell,\
  \ \u05DE\u05D0\u05E4\u05E9\u05E8\u05D9\u05DD \u05DC\u05DA \u05DC\u05D0\u05D7\u05E1\
  \u05DF \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD \u05D1\u05D6\u05D5\u05D2\u05D5\u05EA\
  \ \u05DE\u05E4\u05EA\u05D7-\u05E2\u05E8\u05DA, \u05DE\u05D4 \u05E9\u05D4\u05D5\u05E4\
  \u05DA \u05D0\u05EA \u05D0\u05D7\u05D6\u05D5\u05E8 \u05D4\u05E0\u05EA\u05D5\u05E0\
  \u05D9\u05DD \u05DC\u05E4\u05E9\u05D5\u05D8 \u05D5\u05D9\u05E2\u05D9\u05DC."
title: "\u05E9\u05D9\u05DE\u05D5\u05E9 \u05D1\u05DE\u05E2\u05E8\u05DB\u05D9\u05DD\
  \ \u05D0\u05E1\u05D5\u05E6\u05D9\u05D0\u05D8\u05D9\u05D1\u05D9\u05D9\u05DD"
weight: 15
---

## איך ל:
יצירה ושימוש במערכים אסוציאטיביים ב-PowerShell היא די ישירה. כך עושים את הקסם:

**יצירת מערך אסוציאטיבי:**

```PowerShell
$myAssociativeArray = @{}
$myAssociativeArray["name"] = "Alex"
$myAssociativeArray["age"] = 25
$myAssociativeArray["job"] = "Engineer"
```

קטע הקוד הזה יוצר מערך אסוציאטיבי עם שלושה זוגות מפתח-ערך.

**גישה לערכים:**

כדי לקבל ערך, הפנה למפתח שלו:

```PowerShell
Write-Output $myAssociativeArray["name"]
```

**פלט לדוגמה:**

```
Alex
```

**הוספה או שינוי נתונים:**

פשוט השתמש במפתח כדי להוסיף זוג חדש או לשנות זוג קיים:

```PowerShell
$myAssociativeArray["location"] = "New York" # מוסיף זוג מפתח-ערך חדש
$myAssociativeArray["job"] = "Senior Engineer" # משנה זוג קיים
```

**עיבוד של מערך אסוציאטיבי:**

עובר על מפתחות וערכים כך:

```PowerShell
foreach ($key in $myAssociativeArray.Keys) {
  $value = $myAssociativeArray[$key]
  Write-Output "$key : $value"
}
```

**פלט לדוגמה:**

```
name : Alex
age : 25
job : Senior Engineer
location : New York
```

## טבילה עמוקה
המושג של מערכים אסוציאטיביים מוכר ברחבי שפות תכנות רבות, בדרך כלל נקרא מילון, מפה, או טבלת גיבוב תלוי בשפה. ב-PowerShell, מערכים אסוציאטיביים מיושמים כטבלאות גיבוב, אשר יעילות מאוד לחיפוש מפתחות, אחסון נתונים ושמירה על אוסף של מפתחות ייחודיים.

בהיסטוריה, מערכים אסוציאטיביים מספקים אמצעי לנהל אוספים של אובייקטים שכל פריט בהם ניתן לאחזור במהירות ללא ניהול על פני כל האוסף, באמצעות מפתחו. היעילות של אחזור ושינוי נתונים במערכים אסוציאטיביים הופכת אותם לבחירה מועדפת למשימות שונות. עם זאת, יש להם הגבלות, כמו לשמור על סדר, שלשם כך מילונים מסודרים או אובייקטים מותאמים אישית יכולים להיות חלופה טובה יותר.

למרות ההגבלות שלהם, מערכים אסוציאטיביים / טבלאות גיבוב ב-PowerShell הם גמישים וכלי עוצמתי מאוד לסקריפטינג. הם מאפשרים אחסון נתונים דינמי ובמיוחד שימושיים בהגדרות, עיבוד נתונים, ובכל מקום שנדרש פורמט נתונים מובנה ללא העלות של הגדרת מחלקה רשמית. זכור, בזמן שמערכים אסוציאטיביים מושלמים לאחזור המבוסס על מפתח, אם המשימה שלך כוללת מבני נתונים מורכבים או דורשת שמירה על סדר ספציפי, ייתכן שתרצה לחקור סוגי נתונים אחרים או אובייקטים מותאמים אישית בתוך PowerShell.
