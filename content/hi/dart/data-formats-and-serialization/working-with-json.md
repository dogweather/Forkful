---
title:                "JSON के साथ काम करना"
date:                  2024-03-08T21:58:26.009439-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?

JSON (जावास्क्रिप्ट ऑब्जेक्ट नोटेशन) के साथ कार्य करना डार्ट ऑब्जेक्ट्स में स्ट्रिंग्स से JSON डेटा पार्स करने और इसके विपरीत का कार्य शामिल है, जो कि वेब और ऐप विकास में डेटा इंटरचेंज के लिए एक सामान्य कार्य है। प्रोग्रामर्स इसे एपीआई, कॉन्फिगरेशन, या उनके ऐप्स के अंदर घटकों के बीच संवाद के डेटा को कुशलतापूर्वक संभालने के लिए करते हैं।

## कैसे करें:

डार्ट `dart:convert` लाइब्रेरी के साथ JSON के लिए निर्मित सहायता प्रदान करता है, जिससे JSON को एनकोड और डिकोड करना सीधा है। नीचे बुनियादी कार्यों को दर्शाने वाले उदाहरण दिए गए हैं:

**JSON स्ट्रिंग को डार्ट ऑब्जेक्ट में पार्स करना:**
```dart
import 'dart:convert';

void main() {
  // उदाहरण JSON स्ट्रिंग
  String jsonString = '{"name": "John", "age": 30, "email": "john@example.com"}';
  
  // JSON को डार्ट मैप में डिकोड करना
  Map<String, dynamic> user = jsonDecode(jsonString);
  
  print('Hello, ${user['name']}! आप ${user['age']} वर्ष के हैं।');
  // आउटपुट: Hello, John! आप 30 वर्ष के हैं।
}
```

**डार्ट ऑब्जेक्ट को JSON स्ट्रिंग में एनकोड करना:**
```dart
import 'dart:convert';

void main() {
  // उदाहरण डार्ट ऑब्जेक्ट
  Map<String, dynamic> user = {
    'name': 'Jane',
    'age': 25,
    'email': 'jane@example.com'
  };
  
  // डार्ट मैप को JSON में एनकोडिंग
  String jsonString = jsonEncode(user);
  
  print(jsonString);
  // आउटपुट: {"name":"Jane","age":25,"email":"jane@example.com"}
}
```

**जटिल मॉडल्स के लिए `json_serializable` का उपयोग करना:**
जटिल डेटा मॉडल्स के लिए, मैन्युअल सीरियलाइजेशन बहुत थकाऊ हो सकता है। `json_serializable` पैकेज इस प्रक्रिया को स्वचालित करता है। इसके लिए अतिरिक्त सेटअप की आवश्यकता होती है, जिसमें आपके `pubspec.yaml` में निर्भरताएँ जोड़ना और बिल्ड फाइलें बनाना शामिल है। सेटअप के बाद, आप इसे निम्नलिखित तरीके से उपयोग कर सकते हैं:

1. एनोटेशन के साथ एक मॉडल परिभाषित करें:
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

2. धारावाहिकीकरण बॉयलरप्लेट उत्पन्न करें:
`user.g.dart` फाइल उत्पन्न करने के लिए बिल्ड रनर कमांड का उपयोग करें:
```shell
flutter pub run build_runner build
```

3. अपने मॉडल का उपयोग करें:
```dart
void main() {
  // User को JSON में पार्स करना
  Map userMap = jsonDecode('{"name": "John", "age": 30, "email": "john@example.com"}');
  User user = User.fromJson(userMap);
  
  print('User: ${user.name}, Age: ${user.age}');
  // आउटपुट: User: John, Age: 30

  // User को वापस JSON में परिवर्तित करना
  String jsonString = jsonEncode(user.toJson());
  print(jsonString);
  // आउटपुट: {"name":"John","age":30,"email":"john@example.com"}
}
```

ये उदाहरण डार्ट में बुनियादी और उन्नत JSON सहभागिता को दर्शाते हैं, विकासकर्ताओं को उनके एप्लिकेशन में डेटा धारावाहिकीकरण कार्यों को सहजतापूर्वक संभालने के लिए सशक्त बनाते हैं।
