---
title:                "वेब पेज डाउनलोड करना"
date:                  2024-03-08T21:54:43.295222-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?

वेब पेज को डाउनलोड करने का अर्थ है, उसके URL के माध्यम से एक वेब पेज की सामग्री को लाना और उसका प्रोसेसिंग या संग्रहण करना। प्रोग्रामर इसे जानकारी निकालने, परिवर्तनों की निगरानी करने, या सामग्री को संग्रहीत करने के लिए करते हैं, जिससे यह वेब स्क्रेपिंग, डेटा माइनिंग, और स्वचालित परीक्षण कार्यों में एक मुख्य घटक बन जाता है।

## कैसे करें:

Dart एक लोकप्रिय तृतीय-पक्ष पुस्तकालय `http` पैकेज प्रदान करता है, जो HTTP अनुरोधों को करने के लिए है। यहां एक वेबपेज को डाउनलोड करने के लिए इसका उपयोग कैसे करें, का एक मौलिक उदाहरण दिया गया है:

सबसे पहले, अपनी `pubspec.yaml` में `http` पैकेज जोड़ें:
```
dependencies:
  http: ^0.13.3
```

फिर, पैकेज को इम्पोर्ट करें और इसका उपयोग एक वेब पेज की सामग्री को लाने के लिए करें:

```dart
import 'package:http/http.dart' as http;

Future<void> main() async {
  var url = Uri.parse('http://example.com');
  var response = await http.get(url);
  if (response.statusCode == 200) {
    print('पेज डाउनलोड हुआ:');
    print(response.body);
  } else {
    print('अनुरोध विफल रहा, स्थिति: ${response.statusCode}.');
  }
}
```

**नमूना आउटपुट** (यह वेब पेज की सामग्री के आधार पर भिन्न होगा):
```
पेज डाउनलोड हुआ:
<!doctype html>
<html>
<head>
    <title>Example Domain</title>
...
</html>
```

कूकीज़ को संभालने या यूज़र-एजेंट हेडर्स सेट करने जैसे अधिक जटिल परिस्थितियों के लिए, आप अपने अनुरोध में अतिरिक्त कॉन्फ़िगरेशन के साथ उसी `http` पैकेज का उपयोग करेंगे:
```dart
import 'package:http/http.dart' as http;

Future<void> main() async {
  var headers = {
    'User-Agent': 'YourCustomUserAgent/1.0',
    'Cookie': 'name=value; name2=value2',
  };
  var url = Uri.parse('http://example.com');
  var response = await http.get(url, headers: headers);

  if (response.statusCode == 200) {
    print('पेज कस्टम हेडर्स के साथ डाउनलोड हुआ:');
    print(response.body);
  } else {
    print('अनुरोध विफल रहा, स्थिति: ${response.statusCode}.');
  }
}
```

इस तरह के हेडर्स का उपयोग करके आप ब्राउज़र अनुरोधों की अधिक सटीक नकल कर सकते हैं, जो विशेष आवश्यकताओं या स्क्रेपिंग के खिलाफ सुरक्षाओं वाली साइटों से निपटने में विशेष रूप से उपयोगी है।
