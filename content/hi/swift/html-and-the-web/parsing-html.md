---
date: 2024-01-20 15:34:42.377782-07:00
description: "HTML \u092A\u093E\u0930\u094D\u0938\u093F\u0902\u0917 \u0935\u0947\u092C\
  \u0938\u093E\u0907\u091F \u0915\u0947 \u0921\u093E\u091F\u093E \u0915\u094B \u0938\
  \u0902\u0938\u094D\u0915\u0930\u093F\u0924 \u0915\u0930\u0928\u0947 \u0915\u0940\
  \ \u092A\u094D\u0930\u0915\u094D\u0930\u093F\u092F\u093E \u0939\u0948\u0964 \u092A\
  \u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u0910\u0938\u093E\
  \ \u0924\u092C \u0915\u0930\u0924\u0947 \u0939\u0948\u0902 \u091C\u092C \u0909\u0928\
  \u094D\u0939\u0947\u0902 \u0935\u0947\u092C \u092A\u0947\u091C \u0938\u0947 \u0938\
  \u093E\u092E\u0917\u094D\u0930\u0940 \u0928\u093F\u0915\u093E\u0932\u0928\u0940\
  \ \u0939\u094B\u0924\u0940 \u0939\u0948\u0964"
lastmod: '2024-03-13T22:44:52.914524-06:00'
model: unknown
summary: "HTML \u092A\u093E\u0930\u094D\u0938\u093F\u0902\u0917 \u0935\u0947\u092C\
  \u0938\u093E\u0907\u091F \u0915\u0947 \u0921\u093E\u091F\u093E \u0915\u094B \u0938\
  \u0902\u0938\u094D\u0915\u0930\u093F\u0924 \u0915\u0930\u0928\u0947 \u0915\u0940\
  \ \u092A\u094D\u0930\u0915\u094D\u0930\u093F\u092F\u093E \u0939\u0948\u0964 \u092A\
  \u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u0910\u0938\u093E\
  \ \u0924\u092C \u0915\u0930\u0924\u0947 \u0939\u0948\u0902 \u091C\u092C \u0909\u0928\
  \u094D\u0939\u0947\u0902 \u0935\u0947\u092C \u092A\u0947\u091C \u0938\u0947 \u0938\
  \u093E\u092E\u0917\u094D\u0930\u0940 \u0928\u093F\u0915\u093E\u0932\u0928\u0940\
  \ \u0939\u094B\u0924\u0940 \u0939\u0948\u0964."
title: "HTML \u092A\u093E\u0930\u094D\u0938 \u0915\u0930\u0928\u093E"
weight: 43
---

## How to: (कैसे करें:)
Swift में HTML पार्स करने के लिए हम SwiftSoup जैसे third-party लाइब्रेरी का उपयोग कर सकते हैं। 

पहले CocoaPods या Swift Package Manager से SwiftSoup इंस्टॉल करें।

फिर, SwiftSoup का इस्तेमाल करते हुए HTML से डेटा निकालना इस प्रकार होगा:

```Swift
import SwiftSoup

let htmlString = """
    <html>
        <head>
            <title>नमस्ते Swift</title>
        </head>
        <body>
            <p class='greeting'>Hello, World!</p>
        </body>
    </html>
    """

do {
    let doc: Document = try SwiftSoup.parse(htmlString)
    if let title = try doc.title() {
        print(title)  // Output: नमस्ते Swift
    }
    
    if let greeting = try doc.getElementsByClass("greeting").first()?.text() {
        print(greeting)  // Output: Hello, World!
    }
} catch Exception.Error(let type, let message) {
    print("Type: \(type)")
    print("Message: \(message)")
} catch {
    print("error")
}
```

## Deep Dive (विस्तार से जानकारी):
HTML पार्सिंग की आवश्यकता तब आती है जब हमें वेबडेटा को अपने एप्लीकेशन के फॉर्मेट में बदलना होता है। पुराने समय में, रेगेक्स (Regular Expressions) का इस्तेमाल होता था, पर वह अविश्वसनीय और जटिल था। SwiftSoup जैसी लाइब्रेरीज ने इस काम को आसान और अधिक सटीक बना दिया है। DOM (Document Object Model) पर आधारित ये लाइब्रेरीज parse, search, और manipulate HTML को अधिक सहजता से करने में हमारी मदद करती हैं।

## See Also (अन्य संसाधन):
- SwiftSoup गिटहब पेज: [SwiftSoup on GitHub](https://github.com/scinfu/SwiftSoup)
- HTML पार्सिंग के लिए XMLParser डॉक्युमेंटेशन: [Apple's XMLParser](https://developer.apple.com/documentation/foundation/xmlparser)
- Swift के SPM (Swift Package Manager) के बारे में जानकारी: [Swift Package Manager](https://swift.org/package-manager/)
