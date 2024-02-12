---
title:                "YAML के साथ काम करना"
aliases:
- /hi/swift/working-with-yaml/
date:                  2024-02-03T19:27:48.930190-07:00
model:                 gpt-4-0125-preview
simple_title:         "YAML के साथ काम करना"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/swift/working-with-yaml.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?
YAML, जिसका पूरा नाम YAML Ain't Markup Language है, सभी प्रोग्रामिंग भाषाओं के लिए एक मानव-हितैषी डेटा सीरियलाइजेशन मानक है। प्रोग्रामर इसे कॉन्फ़िगरेशन फाइलों, अंतर-प्रक्रिया संदेशवाहन, और डेटा स्टोरेज के लिए उपयोग करते हैं क्योंकि इसकी पठनीयता अन्य डेटा प्रारूपों जैसे कि XML या JSON की तुलना में व्यावहारिक अंग्रेजी के बहुत करीब है, जिससे इसे समझना और लिखना आसान हो जाता है।

## कैसे करें:
Swift में YAML पार्सिंग और सीरियलाइजेशन के लिए बिल्ट-इन सपोर्ट शामिल नहीं है, इसलिए तीसरे पक्ष की लाइब्रेरीज का उपयोग आवश्यकता होती है। एक लोकप्रिय विकल्प `Yams` है, जो Swift में YAML के साथ काम करने के लिए एक पुस्तकालय है।

पहले, आपको अपने प्रोजेक्ट में `Yams` जोड़ने की आवश्यकता है। यदि आप Swift Package Manager का उपयोग कर रहे हैं, तो आप इसे अपनी `Package.swift` फ़ाइल में एक निर्भरता के रूप में जोड़ सकते हैं:

```swift
dependencies: [
    .package(url: "https://github.com/jpsim/Yams.git", from: "4.0.0")
]
```

### Swift में YAML पार्स करना
मान लें कि आपके पास एक सरल ऐप के लिए निम्नलिखित YAML कॉन्फ़िगरेशन है:

```yaml
name: MyApp
version: 1.0
environment: development
features:
  - login
  - notifications
```

`Yams` का उपयोग करके Swift में इस YAML स्ट्रिंग को कैसे पार्स करें, यहाँ देखें:

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
        // पार्स किए गए डेटा तक पहुँचने का उदाहरण
        if let name = data["name"] as? String {
            print("App Name: \(name)")
        }
    }
} catch {
    print("YAML पार्स करने में त्रुटि: \(error)")
}
```

नमूना आउटपुट:

```
["name": MyApp, "version": 1.0, "environment": "development", "features": ["login", "notifications"]]
App Name: MyApp
```

### Swift ऑब्जेक्ट्स को YAML में सीरियलाइज करना
`Yams` के साथ Swift ऑब्जेक्ट को वापस एक YAML स्ट्रिंग में परिवर्तित करना भी सीधा है। मान लें आपके पास वही डेटा संरचना है जिसे सीरियलाइज किया जाना है:

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
    print("YAML में सीरियलाइज करने में त्रुटि: \(error)")
}
```

यह एक YAML-फॉर्मेटेड स्ट्रिंग उत्पन्न करेगा:

```yaml
environment: development
features:
  - login
  - notifications
name: MyApp
version: 1.0
```

ये उदाहरण Swift एप्लिकेशन्स में YAML के साथ काम करने के बुनियादी ऑपरेशन दिखाते हैं। याद रखें, जबकि YAML मानव पढ़ाई और उपयोग में आसानी में उत्कृष्ट है, अपने एप्लिकेशन की विशिष्ट आवश्यकताओं का विशेष रूप से प्रदर्शन और जटिलता के संबंध में चुनाव करते समय हमेशा ध्यान में रखें, जब आप अपना डेटा सीरियलाइजेशन प्रारूप चुनें।
