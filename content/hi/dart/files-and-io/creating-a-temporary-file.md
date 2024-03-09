---
title:                "अस्थायी फ़ाइल बनाना"
date:                  2024-03-08T21:54:58.014752-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?
Dart में एक अस्थायी फ़ाइल बनाना इस प्रकार की फ़ाइल को उत्पन्न करना शामिल है जो कम समय के लिए इरादा की गई होती है, मुख्य रूप से डेटा केशिंग, फ़ाइल प्रोसेसिंग के लिए अस्थायी संग्रहण या ऐसी जानकारी रखने के लिए जो दीर्घकालिक रखने के लिए बहुत संवेदनशील होती है, जैसे परिदृश्यों में होती है। प्रोग्रामर इसे उन डेटा को प्रबंधित करने के लिए करते हैं जिन्हें स्थायी संग्रहण की आवश्यकता नहीं होती है, इससे प्रदर्शन में सुधार होता है और डेटा स्वच्छता बनी रहती है।

## कैसे:
डार्ट की `dart:io` लाइब्रेरी अस्थायी फ़ाइलों को बनाने में `Directory` क्लास के माध्यम से सुविधा प्रदान करती है। यहाँ एक अस्थायी फ़ाइल बनाने और उसमें कुछ सामग्री लिखने का एक सरल तरीका है:

```dart
import 'dart:io';

Future<void> main() async {
  // एक अस्थायी डायरेक्टरी बनाएं (सिस्टम-विशिष्ट स्थान)
  Directory tempDir = await Directory.systemTemp.createTemp('my_temp_dir_');

  // उस डायरेक्टरी के भीतर एक अस्थायी फ़ाइल बनाएं
  File tempFile = File('${tempDir.path}/my_temp_file.txt');

  // अस्थायी फ़ाइल में कुछ सामग्री लिखें
  await tempFile.writeAsString('This is some temporary content');

  print('अस्थायी फ़ाइल बनाई गई: ${tempFile.path}');

  // नमूना आउटपुट: अस्थायी फ़ाइल बनाई गई: /tmp/my_temp_dir_A1B2C3/my_temp_file.txt
}
```

### तृतीय-पक्ष लाइब्रेरी का उपयोग करना: `path_provider`

विशेष रूप से ऐप्लिकेशन (खासकर Flutter के साथ मोबाइल ऐप्स) के लिए, आप एक अधिक एकीकृत और प्रबंधनीय तरीके से अस्थायी फ़ाइलें बनाना चाह सकते हैं। `path_provider` पैकेज अलग-अलग प्लेटफॉर्मों (iOS, Android, आदि) पर सही अस्थायी डायरेक्टरी खोजने में आपकी मदद कर सकता है।

पहले, अपने `pubspec.yaml` में निर्भरताओं के अंतर्गत `path_provider` जोड़ें:

```yaml
dependencies:
  path_provider: ^2.0.9
```

और यहाँ है कि कैसे आप इसका उपयोग कर एक अस्थायी फ़ाइल बना सकते हैं:

```dart
import 'dart:io';
import 'package:path_provider/path_provider.dart';

Future<void> main() async {
  // अस्थायी डायरेक्टरी प्राप्त करें
  final Directory tempDir = await getTemporaryDirectory();

  // उस डायरेक्टरी के भीतर एक अस्थायी फ़ाइल बनाएं
  final File tempFile = File('${tempDir.path}/my_temp_file.txt');

  // अस्थायी फ़ाइल में कुछ सामग्री लिखें
  await tempFile.writeAsString('This is some temporary content with path_provider');

  print('path_provider के साथ अस्थायी फ़ाइल बनाई गई: ${tempFile.path}');

  // नमूना आउटपुट: path_provider के साथ अस्थायी फ़�इल बनाई गई: /tmp/my_temp_file.txt (पथ प्लेटफ़ॉर्म द्वारा भिन्न हो सकता है)
}
```

ये स्निपेट्स Dart में अस्थायी फ़ाइलों को बनाने और उनके साथ बातचीत करने का वर्णन करते हैं, जो अल्पकालिक उद्देश्यों के लिए डाटा प्रबंधन के लिए एक सीधा और व्यावहारिक दृष्टिकोण प्रदान करता है।
