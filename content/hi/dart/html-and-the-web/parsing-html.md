---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:55:38.100531-07:00
description: "\u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u093F\u0902\u0917\
  \ \u092E\u0947\u0902 HTML \u092A\u093E\u0930\u094D\u0938\u093F\u0902\u0917 \u0915\
  \u093E \u092E\u0924\u0932\u092C \u0939\u0948 HTML \u0926\u0938\u094D\u0924\u093E\
  \u0935\u0947\u091C\u093C\u094B\u0902 \u0938\u0947 \u0921\u0947\u091F\u093E \u0928\
  \u093F\u0915\u093E\u0932\u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\
  \u093E\u092E\u0930 \u0907\u0938\u0947 \u0935\u0947\u092C \u0938\u093E\u092E\u0917\
  \u094D\u0930\u0940 \u0915\u0947 \u0938\u093E\u0925 \u092C\u093E\u0924\u091A\u0940\
  \u0924 \u0915\u0930\u0928\u0947 \u092F\u093E \u0938\u0942\u091A\u0928\u093E \u0928\
  \u093F\u0937\u094D\u0915\u0930\u094D\u0937\u0923, \u092A\u0930\u0940\u0915\u094D\
  \u0937\u0923, \u092F\u093E\u2026"
lastmod: '2024-03-13T22:44:51.809265-06:00'
model: gpt-4-0125-preview
summary: "\u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u093F\u0902\u0917\
  \ \u092E\u0947\u0902 HTML \u092A\u093E\u0930\u094D\u0938\u093F\u0902\u0917 \u0915\
  \u093E \u092E\u0924\u0932\u092C \u0939\u0948 HTML \u0926\u0938\u094D\u0924\u093E\
  \u0935\u0947\u091C\u093C\u094B\u0902 \u0938\u0947 \u0921\u0947\u091F\u093E \u0928\
  \u093F\u0915\u093E\u0932\u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\
  \u093E\u092E\u0930 \u0907\u0938\u0947 \u0935\u0947\u092C \u0938\u093E\u092E\u0917\
  \u094D\u0930\u0940 \u0915\u0947 \u0938\u093E\u0925 \u092C\u093E\u0924\u091A\u0940\
  \u0924 \u0915\u0930\u0928\u0947 \u092F\u093E \u0938\u0942\u091A\u0928\u093E \u0928\
  \u093F\u0937\u094D\u0915\u0930\u094D\u0937\u0923, \u092A\u0930\u0940\u0915\u094D\
  \u0937\u0923, \u092F\u093E \u0938\u094D\u0935\u091A\u093E\u0932\u0928 \u092A\u094D\
  \u0930\u092F\u094B\u091C\u0928\u094B\u0902 \u0915\u0947 \u0932\u093F\u090F \u0935\
  \u0947\u092C \u0938\u093E\u092E\u0917\u094D\u0930\u0940 \u0938\u0947 \u0921\u0947\
  \u091F\u093E \u0916\u0941\u0930\u091A\u0928\u0947 \u0915\u0947 \u0932\u093F\u090F\
  \ \u0915\u0930\u0924\u0947 \u0939\u0948\u0902, \u092F\u0939\u093E\u0901 \u0924\u0915\
  \ \u0915\u093F \u091C\u092C \u0906\u0927\u093F\u0915\u093E\u0930\u093F\u0915 APIs\
  \ \u0909\u092A\u0932\u092C\u094D\u0927 \u0928\u0939\u0940\u0902 \u0939\u094B\u0924\
  \u0947\u0964."
title: "HTML \u0935\u093F\u0936\u094D\u0932\u0947\u0937\u0923"
weight: 43
---

## कैसे करें:
Dart अपने कोर लाइब्रेरीज़ में HTML पार्सिंग के लिए निर्मित समर्थन प्रदान नहीं करता। हालांकि, आप `html` जैसे तृतीय-पक्ष पैकेज का उपयोग करके HTML दस्तावेज़ों को पार्स और नियंत्रित कर सकते हैं। 

पहले, अपनी `pubspec.yaml` फाइल में `html` पैकेज जोड़ें:

```yaml
dependencies:
  html: ^0.15.0
```

फिर, अपनी Dart फाइल में पैकेज को आयात करें:

```dart
import 'package:html/parser.dart' show parse;
import 'package:html/dom.dart';
```

यहाँ एक बुनियादी उदाहरण दिया गया है जिसमें HTML वाली एक स्ट्रिंग को पार्स करके डेटा निकाला जा रहा है:

```dart
void main() {
  var htmlDocument = """
  <html>
    <body>
      <h1>नमस्ते, Dart!</h1>
      <p>यह एक पैराग्राफ है एक नमूना HTML में</p>
    </body>
  </html>
  """;

  // HTML स्ट्रिंग पार्स करें
  Document document = parse(htmlDocument);

  // डेटा निकालना
  String title = document.querySelector('h1')?.text ?? "कोई शीर्षक नहीं मिला";
  String paragraph = document.querySelector('p')?.text ?? "कोई पैराग्राफ नहीं मिला";

  print('शीर्षक: $title');
  print('पैराग्राफ: $paragraph');
}
```

आउटपुट:

```
शीर्षक: नमस्ते, Dart!
पैराग्राफ: यह एक पैराग्राफ है एक नमूना HTML में
```

वास्तविक विश्व वेब पेजेज़ के साथ बातचीत करने के लिए, आप `html` पार्सिंग को HTTP अनुरोधों (वेब सामग्री लाने के लिए `http` पैकेज का उपयोग करके) के साथ जोड़ सकते हैं। यहाँ एक त्वरित उदाहरण दिया गया है:

सबसे पहले, `html` के साथ `http` पैकेज जोड़ें:

```yaml
dependencies:
  html: ^0.15.0
  http: ^0.13.3
```

फिर, वेब से एक HTML पेज लाकर पार्स करें:

```dart
import 'package:http/http.dart' as http;
import 'package:html/parser.dart' show parse;

void main() async {
  var url = 'https://example.com';
  
  // वेबपेज लाएं
  var response = await http.get(Uri.parse(url));
  
  यदि (response.statusCode == 200) {
    var document = parse(response.body);

    // मान लें कि पेज में <h1> टैग हैं जिनमें आपकी रुचि है
    var headlines = document.querySelectorAll('h1').map((e) => e.text).toList();
    
    print('समाचार शीर्षक: $headlines');
  } else {
    print('अनुरोध विफल हो गया स्थिति के साथ: ${response.statusCode}.');
  }
}
```

नोट: ऊपर दिखाई गई वेब स्क्रेपिंग तकनीक का उपयोग वेबसाइट की सेवा की शर्तों के अनुसार जिम्मेदारीपूर्वक किया जाना चाहिए।
