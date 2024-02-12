---
title:                "עבודה עם YAML"
date:                  2024-02-03T19:27:31.568694-07:00
model:                 gpt-4-0125-preview
simple_title:         "עבודה עם YAML"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/he/swift/working-with-yaml.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## מה ולמה?
YAML, שמשמעותו "YAML Ain't Markup Language" (YAML אינו שפת סימון), הוא תקן סידור נתונים ידידותי לאדם לכל שפות התכנות. תכנתיים נוהגים להשתמש בו לקבצי תצורה, הודעות בין-תהליכיות ואחסון נתונים מכיוון שהתמצאותו הרבה יותר קרובה לאנגלית פשוטה בהשוואה לפורמטים אחרים כמו XML או JSON, מה שהופך אותו לפשוט יותר להבנה ולכתיבה.

## איך לעשות:
Swift לא כוללת תמיכה מובנית לפענוח והסרה פלטת נתונים ב-YAML, מה שמחייב שימוש בספריות צד שלישי. בחירה פופולרית היא `Yams`, ספרייה לעבודה עם YAML ב-Swift.

ראשית, אתה צריך להוסיף `Yams` לפרויקט שלך. אם אתה משתמש ב-Swift Package Manager, תוכל להוסיף אותו כתלות בקובץ `Package.swift` שלך:

```swift
dependencies: [
    .package(url: "https://github.com/jpsim/Yams.git", from: "4.0.0")
]
```

### פענוח YAML ל-Swift
נניח שיש לך את התצורה YAML הבאה לאפליקציה פשוטה:

```yaml
name: MyApp
version: 1.0
environment: development
features:
  - login
  - notifications
```

הנה איך תוכל לפענח מחרוזת YAML זו ב-Swift באמצעות `Yams`:

```swift
import Yams

let yamlString = """
name: MyApp
version: 1.0
environment: development
features:
  - login
  - notifications
"""

do {
    if let data = try Yams.load(yaml: yamlString) as? [String: Any] {
        print(data)
        // דוגמה לגישה לנתונים שנפענחו
        if let name = data["name"] as? String {
            print("שם האפליקציה: \(name)")
        }
    }
} catch {
    print("שגיאה בפענוח YAML: \(error)")
}
```

פלט לדוגמה:

```
["name": MyApp, "version": 1.0, "environment": "development", "features": ["login", "notifications"]]
שם האפליקציה: MyApp
```

### הסרה פלטת של אובייקטי Swift ל-YAML
המרת אובייקט של Swift חזרה למחרוזת YAML היא גם קלה עם `Yams`. נניח שיש לך את אותה מבנה נתונים שצריך להיות מוסר פלט:

```swift
let appInfo = [
    "name": "MyApp",
    "version": 1.0,
    "environment": "development",
    "features": ["login", "notifications"]
] as [String : Any]

do {
    let yamlString = try Yams.dump(object: appInfo)
    print(yamlString)
} catch {
    print("שגיאה בהסרה פלטת ל-YAML: \(error)")
}
```

זה יפיק מחרוזת בפורמט YAML:

```yaml
environment: development
features:
  - login
  - notifications
name: MyApp
version: 1.0
```

דוגמאות אלה מדגימות פעולות בסיסיות לעבודה עם YAML ביישומי Swift. זכור, בעוד ש-YAML מצטיין בקריאות לאדם ובנוחות שימוש, תמיד שקול את הצרכים הספציפיים של היישום שלך, במיוחד לגבי ביצועים ומורכבות, כאשר אתה בוחר את פורמט הסידור הנתונים שלך.
