---
title:                "डायरेक्टरी का अस्तित्व जाँचना"
date:                  2024-01-20T14:59:34.057191-07:00
simple_title:         "डायरेक्टरी का अस्तित्व जाँचना"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/swift/checking-if-a-directory-exists.md"
---

{{< edit_this_page >}}

## What & Why? (क्या और क्यों?)
डिरेक्टरी की जांच करना मतलब है पता करना कि कोई फोल्डर मौजूद है कि नहीं। प्रोग्रामर्स इसे इसलिए करते हैं ताकि वे यह सुनिश्चित कर सकें कि फाइल ऑपरेशन्स करने से पहले वांछित डिरेक्ट्री उपस्थित है।

## How to: (कैसे करें?)
```swift
import Foundation

let fileManager = FileManager.default
let path = "/path/to/your/directory"

if fileManager.fileExists(atPath: path, isDirectory: nil) {
    print("Directory exists 📁")
} else {
    print("Directory does not exist ❌")
}
```
सैंपल आउटपुट:
```
Directory exists 📁
```
या
```
Directory does not exist ❌
```

## Deep Dive (गहराई से जानकारी)
पहले के समय में डिरेक्ट्री चेक करने के लिए अलग तरीके थे, जैसे कि टर्मिनल कमांड्स का उपयोग करके। अब, `FileManager` जैसे स्विफ्ट उपकरणों ने इसे आसान बना दिया है। ऊपर दिए गए कोड में, `fileManager.fileExists(atPath:isDirectory:)` आपको बताता है कि कोई फाइल या डिरेक्टरी मौजूद है या नहीं, और `isDirectory` पैरामीटर का उपयोग करके, आप यह स्पष्ट कर सकते हैं कि आप एक डिरेक्टरी की जांच कर रहे हैं या नहीं। यह एप्रोच न केवल स्विफ्ट में सामान्य है, बल्कि यह सुरक्षित और विश्वसनीय भी है।

## See Also (और देखें)
- [Apple Documentation for FileManager](https://developer.apple.com/documentation/foundation/filemanager)
- [Swift Language Guide](https://docs.swift.org/swift-book/LanguageGuide/TheBasics.html)
- [StackOverflow discussion on checking directories in Swift](https://stackoverflow.com/questions/24034544/dispatch-a-high-priority-task-in-global-qos-class)
