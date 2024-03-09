---
title:                "बेसिक प्रमाणन के साथ HTTP अनुरोध भेजना"
date:                  2024-03-08T21:56:55.086846-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?

HTTP अनुरोध के साथ मूल प्रमाणीकरण भेजना उपयोगकर्ता की पहचान की पुष्टि करने के लिए एक अनुरोध के साथ एक उपयोगकर्ता नाम और पासवर्ड को संलग्न करने की प्रक्रिया है। प्रोग्रामर इसे प्रमाणीकरण की आवश्यकता वाले संसाधनों तक पहुँचने के लिए उपयोग करते हैं, सुनिश्चित करते हैं कि ग्राहक और सर्वर के बीच सुरक्षित संचार होता है।

## कैसे करें:

डार्ट में, आप `http` पैकेज का उपयोग करके मूल प्रमाणीकरण के साथ HTTP अनुरोध भेज सकते हैं। पहले, अपनी `pubspec.yaml` फाइल में `http` पैकेज जोड़ें:

```yaml
dependencies:
  http: ^0.13.4
```

फिर, अपनी Dart फाइल में पैकेज को आयात करें:

```dart
import 'package:http/http.dart' as http;
import 'dart:convert';
```

मूल प्रमाणीकरण के साथ एक GET अनुरोध भेजने के लिए, आप निम्नलिखित कोड का उपयोग कर सकते हैं:

```dart
Future<void> fetchUserData() async {
  final username = 'yourUsername';
  final password = 'yourPassword';
  final credentials = base64Encode(utf8.encode('$username:$password'));
  final response = await http.get(
    Uri.parse('https://yourapi.com/userdata'),
    headers: {
      'Authorization': 'Basic $credentials',
    },
  );

  if (response.statusCode == 200) {
    print('उपयोगकर्ता का डाटा सफलतापूर्वक लाया गया!');
    print('प्रतिक्रिया शरीर: ${response.body}');
  } else {
    print('उपयोगकर्ता डाटा लाने में विफल रहा, स्थिति कोड के साथ: ${response.statusCode}');
  }
}
```

यह कोड 'https://yourapi.com/userdata' पर एक GET अनुरोध भेजता है जिसमें एक मूल प्रमाणीकरण हैडर होता है। उपयोगकर्ता नाम और पासवर्ड को base64 में एन्कोड किया गया है और 'Authorization' हैडर में मूल एक्सेस प्रमाणीकरण मानकों के अनुसार दिया गया है।

**नमूना आउटपुट:**

सफल अनुरोध पर और यदि सर्वर 200 का स्थिति कोड वापस करता है, आप देख सकते हैं:

```plaintext
उपयोगकर्ता का डाटा सफलतापूर्वक लाया गया!
प्रतिक्रिया शरीर: {"id":1, "name":"John Doe", "email":"john@example.com"}
```

यदि प्रमाणीकरण विफल होता है या कोई अन्य त्रुटि होती है, तो प्रतिक्रिया स्थिति कोड समस्या की पहचान करने में मदद करेगा।
