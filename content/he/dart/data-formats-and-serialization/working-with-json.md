---
title:                "עבודה עם JSON"
date:                  2024-03-08T21:58:04.663201-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## מה ולמה?

עבודה עם JSON (JavaScript Object Notation) כוללת פיענוח נתוני JSON ממחרוזות אל אובייקטים של Dart ולהפך, משימה נפוצה בפיתוח אינטרנט ואפליקציות להחלפת נתונים. תכנתים עושים זאת כדי לנהל נתונים בצורה יעילה מ-APIs, הגדרות או תקשורת בין רכיבים בתוך האפליקציות שלהם.

## איך לעשות:

Dart מספקת תמיכה מובנית ל-JSON עם הספריה `dart:convert`, ומקלה על קידוד ופענוח של JSON. להלן דוגמאות המדגימות פעולות בסיסיות:

**פיענוח מחרוזת JSON לאובייקט של Dart:**
```dart
import 'dart:convert';

void main() {
  // דוגמת מחרוזת JSON
  String jsonString = '{"name": "John", "age": 30, "email": "john@example.com"}';
  
  // פענוח JSON ל-Map של Dart
  Map<String, dynamic> user = jsonDecode(jsonString);
  
  print('שלום, ${user['name']}! הנך בן ${user['age']} שנים.');
  // פלט: שלום, John! הנך בן 30 שנים.
}
```

**קידוד אובייקט של Dart למחרוזת JSON:**
```dart
import 'dart:convert';

void main() {
  // דוגמת אובייקט של Dart
  Map<String, dynamic> user = {
    'name': 'Jane',
    'age': 25,
    'email': 'jane@example.com'
  };
  
  // קידוד Map של Dart ל-JSON
  String jsonString = jsonEncode(user);
  
  print(jsonString);
  // פלט: {"name":"Jane","age":25,"email":"jane@example.com"}
}
```

**שימוש ב-`json_serializable` למודלים מורכבים:**
עבור מודלים מורכבים, סידור ידני יכול להיות מסובך. החבילה `json_serializable` מאטמטת את התהליך הזה. היא דורשת הגדרה נוספת, כולל הוספת תלות ב-`pubspec.yaml` שלך ויצירת קבצי בנייה. לאחר ההגדרה, ניתן להשתמש בה כדלקמן:

1. הגדרת מודל עם הערות:
```dart
import 'package:json_annotation/json_annotation.dart';

part 'user.g.dart';

@JsonSerializable()
class User {
  String name;
  int age;
  String email;
  
  User({required this.name, required this.age, required this.email});
  
  factory User.fromJson(Map<String, dynamic> json) => _$UserFromJson(json);
  Map<String, dynamic> toJson() => _$UserToJson(this);
}
```

2. יצירת הקוד הסטנדרטי לסידור:
השתמש בפקודת ה-build runner ליצירת קובץ ה-`user.g.dart`:
```shell
flutter pub run build_runner build
```

3. השתמש במודל שלך:
```dart
void main() {
  // פיענוח JSON ל-User
  Map userMap = jsonDecode('{"name": "John", "age": 30, "email": "john@example.com"}');
  User user = User.fromJson(userMap);
  
  print('משתמש: ${user.name}, גיל: ${user.age}');
  // פלט: משתמש: John, גיל: 30

  // המרת User בחזרה ל-JSON
  String jsonString = jsonEncode(user.toJson());
  print(jsonString);
  // פלט: {"name":"John","age":30,"email":"john@example.com"}
}
```

דוגמאות אלו ממחישות את האינטראקציות הבסיסיות והמתקדמות עם JSON ב-Dart, מעניקות למפתחים את היכולת לנהל משימות סידור נתונים באפליקציות שלהם בצורה חלקה.
