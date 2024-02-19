---
aliases:
- /he/vba/working-with-json/
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:06:25.432100-07:00
description: "JSON (JavaScript Object Notation) \u05D4\u05D5\u05D0 \u05E4\u05D5\u05E8\
  \u05DE\u05D8 \u05D7\u05D9\u05DC\u05D5\u05E4\u05D9 \u05E0\u05EA\u05D5\u05E0\u05D9\
  \u05DD \u05E7\u05DC \u05DE\u05E9\u05E7\u05DC \u05E9\u05E7\u05DC \u05DC\u05E7\u05E8\
  \u05D9\u05D0\u05D4 \u05D5\u05DC\u05DB\u05EA\u05D9\u05D1\u05D4 \u05E2\u05D1\u05D5\
  \u05E8 \u05D1\u05E0\u05D9 \u05D0\u05D3\u05DD, \u05D5\u05DC\u05E0\u05D9\u05EA\u05D5\
  \u05D7 \u05D5\u05D9\u05D9\u05E6\u05D5\u05E8 \u05E2\u05D1\u05D5\u05E8 \u05DE\u05DB\
  \u05D5\u05E0\u05D5\u05EA. \u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05DE\u05E9\
  \u05EA\u05DE\u05E9\u05D9\u05DD \u05D1-JSON\u2026"
lastmod: 2024-02-18 23:08:52.686130
model: gpt-4-0125-preview
summary: "JSON (JavaScript Object Notation) \u05D4\u05D5\u05D0 \u05E4\u05D5\u05E8\u05DE\
  \u05D8 \u05D7\u05D9\u05DC\u05D5\u05E4\u05D9 \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD\
  \ \u05E7\u05DC \u05DE\u05E9\u05E7\u05DC \u05E9\u05E7\u05DC \u05DC\u05E7\u05E8\u05D9\
  \u05D0\u05D4 \u05D5\u05DC\u05DB\u05EA\u05D9\u05D1\u05D4 \u05E2\u05D1\u05D5\u05E8\
  \ \u05D1\u05E0\u05D9 \u05D0\u05D3\u05DD, \u05D5\u05DC\u05E0\u05D9\u05EA\u05D5\u05D7\
  \ \u05D5\u05D9\u05D9\u05E6\u05D5\u05E8 \u05E2\u05D1\u05D5\u05E8 \u05DE\u05DB\u05D5\
  \u05E0\u05D5\u05EA. \u05DE\u05EA\u05DB\u05E0\u05EA\u05D9\u05DD \u05DE\u05E9\u05EA\
  \u05DE\u05E9\u05D9\u05DD \u05D1-JSON\u2026"
title: "\u05E2\u05D1\u05D5\u05D3\u05D4 \u05E2\u05DD JSON"
---

{{< edit_this_page >}}

## מה ולמה?

JSON (JavaScript Object Notation) הוא פורמט חילופי נתונים קל משקל שקל לקריאה ולכתיבה עבור בני אדם, ולניתוח וייצור עבור מכונות. מתכנתים משתמשים ב-JSON לשידור נתונים בין שרת לאפליקציית רשת או לאחסון מידע בצורה מובנית ונגישה בתוך מגוון סביבות תכנות, כולל Visual Basic for Applications (VBA).

## איך לעשות:

VBA לא תומך באופן טבעי בניתוח או ייצור של JSON, אז נשתמש בשפת סקריפט כמו JScript (דרך אובייקט ScriptControl) לניתוח מחרוזות JSON ובניית אובייקטים של JSON. הנה איך אפשר לנתח מחרוזת JSON ב-VBA:

```basic
Function ParseJSON(ByVal jsonString As String) As Object
    Dim scriptControl As Object
    Set scriptControl = CreateObject("MSScriptControl.ScriptControl")
    scriptControl.Language = "JScript"
    
    scriptControl.Eval "var obj = (" & jsonString & ")"
    Set ParseJSON = scriptControl.CodeObject.obj
End Function

Sub DemoParseJSON()
    Dim jsonString As String
    jsonString = "{""name"":""John"", ""age"":30, ""city"":""New York""}"
    
    Dim parsed As Object
    Set parsed = ParseJSON(jsonString)
    
    MsgBox "Name: " & parsed.name & ", Age: " & parsed.age & ", City: " & parsed.city
End Sub
```

לייצור JSON, אפשר להשתמש בגישה דומה, בנייה של מחרוזת ה-JSON דרך שרשור:

```basic
Function GenerateJSON(name As String, age As Integer, city As String) As String
    GenerateJSON = "{""name"":""" & name & """, ""age"":" & age & ", ""city"":""" & city & """}"
End Function

Sub DemoGenerateJSON()
    Dim jsonString As String
    jsonString = GenerateJSON("Jane", 28, "Los Angeles")
    
    MsgBox jsonString
End Sub
```

## צלילה עמוקה

הגישות שהוצגו מנצלות את ScriptControl כדי לטפל ב-JJSON, כלומר, מעבירות את העבודה למנוע JavaScript. זווית יצירתית אך לא בהכרח הדרך היעילה או המודרנית ביותר לעבוד עם JSON בהקשר של VBA. ביישומים מורכבים יותר, שיטה זו עלולה להפוך למסורבלת ולהוסיף עלויות ביצוע או דאגות בטיחות, מכיוון ש-ScriptControl מתבצע בסביבה שיש לה גישה מלאה למחשב המארח.

סביבות תכנות אחרות, כמו Python או JavaScript, מציעות תמיכה מובנית ל-JJSON, הופכות אותן למתאימות יותר ליישומים שדורשים עיבוד JSON נרחב. שפות אלו מספקות ספריות מקיפות המקלות לא רק על ניתוח וייצור אלא גם על שאילתה ועיצוב של נתוני JSON.

למרות המגבלות הללו ב-VBA, הבנה של איך לעבוד עם JSON היא חיונית בעולם שבו חילופי נתונים מבוססי רשת וקבצי תצורה מתבצעים בעיקר בפורמט JSON. למתכנתי VBA, השליטה בטכניקות אלו פותחת הזדמנויות לשילוב עם ממשקי API של אתרי אינטרנט, לפרשנות של קבצי תצורה, או אפילו לבניית אפליקציות רשת פשוטות. עם זאת, כשפרויקטים גדלים במורכבות או דורשים ביצועים גבוהים, מפתחים עשויים לשקול לנצל סביבות תכנות ידידותיות יותר ל-JJSON.
