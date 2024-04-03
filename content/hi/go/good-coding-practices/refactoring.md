---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:07:30.773456-07:00
description: "\u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u093F\u0902\u0917\
  \ \u092E\u0947\u0902 \u0930\u093F\u092B\u0948\u0915\u094D\u091F\u0930\u093F\u0902\
  \u0917 \u0915\u093E \u092E\u0924\u0932\u092C \u0939\u094B\u0924\u093E \u0939\u0948\
  \ \u092E\u094C\u091C\u0942\u0926\u093E \u0915\u0902\u092A\u094D\u092F\u0942\u091F\
  \u0930 \u0915\u094B\u0921 \u0915\u093E \u092A\u0941\u0928\u0930\u094D\u0917\u0920\
  \u0928\u2014\u0915\u094B\u0921 \u0915\u0940 \u092B\u0948\u0915\u094D\u091F\u0930\
  \u093F\u0902\u0917 \u0915\u094B \u092C\u0926\u0932\u0928\u093E\u2014\u0909\u0938\
  \u0915\u0947 \u092C\u093E\u0939\u0930\u0940 \u0935\u094D\u092F\u0935\u0939\u093E\
  \u0930 \u0915\u094B \u092C\u093F\u0928\u093E \u092C\u0926\u0932\u0947\u0964 \u092A\
  \u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u0907\u0938\u2026"
lastmod: '2024-03-13T22:44:51.448814-06:00'
model: gpt-4-0125-preview
summary: "\u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u093F\u0902\u0917\
  \ \u092E\u0947\u0902 \u0930\u093F\u092B\u0948\u0915\u094D\u091F\u0930\u093F\u0902\
  \u0917 \u0915\u093E \u092E\u0924\u0932\u092C \u0939\u094B\u0924\u093E \u0939\u0948\
  \ \u092E\u094C\u091C\u0942\u0926\u093E \u0915\u0902\u092A\u094D\u092F\u0942\u091F\
  \u0930 \u0915\u094B\u0921 \u0915\u093E \u092A\u0941\u0928\u0930\u094D\u0917\u0920\
  \u0928\u2014\u0915\u094B\u0921 \u0915\u0940 \u092B\u0948\u0915\u094D\u091F\u0930\
  \u093F\u0902\u0917 \u0915\u094B \u092C\u0926\u0932\u0928\u093E\u2014\u0909\u0938\
  \u0915\u0947 \u092C\u093E\u0939\u0930\u0940 \u0935\u094D\u092F\u0935\u0939\u093E\
  \u0930 \u0915\u094B \u092C\u093F\u0928\u093E \u092C\u0926\u0932\u0947\u0964 \u092A\
  \u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u0907\u0938\
  \ \u092A\u094D\u0930\u0915\u094D\u0930\u093F\u092F\u093E \u0915\u094B \u0915\u094B\
  \u0921 \u0915\u0940 \u0938\u092E\u091D\u0928\u0947 \u0915\u0940 \u0906\u0938\u093E\
  \u0928\u0940 \u092E\u0947\u0902 \u0938\u0941\u0927\u093E\u0930, \u091C\u091F\u093F\
  \u0932\u0924\u093E \u0915\u094B \u0915\u092E \u0915\u0930\u0928\u093E, \u0914\u0930\
  \ \u092E\u0947\u0902\u091F\u0947\u0928\u0947\u092C\u093F\u0932\u093F\u091F\u0940\
  \ \u092C\u0922\u093C\u093E\u0928\u0947 \u0915\u0947 \u0932\u093F\u090F \u0905\u092A\
  \u0928\u093E\u0924\u0947 \u0939\u0948\u0902, \u0906\u0916\u093F\u0930\u0915\u093E\
  \u0930 \u0907\u0938\u0938\u0947 \u0938\u0949\u092B\u094D\u091F\u0935\u0947\u092F\
  \u0930 \u0915\u094B \u0938\u092E\u091D\u0928\u093E \u0914\u0930 \u0938\u0902\u0936\
  \u094B\u0927\u093F\u0924 \u0915\u0930\u0928\u093E \u0906\u0938\u093E\u0928 \u0939\
  \u094B \u091C\u093E\u0924\u093E \u0939\u0948\u0964."
title: "\u0930\u0940\u092B\u0948\u0915\u094D\u091F\u0930\u093F\u0902\u0917"
weight: 19
---

## कैसे करें:
Go में, रिफैक्टरिंग साधारण कोड ट्वीक्स से लेकर अधिक जटिल बदलावों तक हो सकती है। चलिए एक मूल उदाहरण से शुरू करें: बेहतर पठनीयता और कार्यक्षमता के लिए एक प्रारंभिक Go फंक्शन को सरल बनाना।

**रिफैक्टरिंग से पहले:**

```go
package main

import "fmt"

func CalculatePrice(quantity int, price float64) float64 {
    var total float64
    if quantity > 0 {
        total = float64(quantity) * price
    } else {
        total = 0
    }
    return total
}

func main() {
    fmt.Println(CalculatePrice(10, 5.99))  // आउटपुट: 59.9
}
```

**रिफैक्टरिंग के बाद:**

```go
package main

import "fmt"

func CalculatePrice(quantity int, price float64) float64 {
    if quantity > 0 {
        return float64(quantity) * price
    }
    return 0
}

func main() {
    fmt.Println(CalculatePrice(10, 5.99))  // आउटपुट: 59.9
}
```

रिफैक्टर किए गए संस्करण में, `else` को हटा दिया गया है, जिससे फ़ंक्शन का प्रवाह सरल हो जाता है बिना इसके आउटपुट को प्रभावित किए—Go में एक मूल लेकिन प्रभावशाली रिफैक्टरिंग तकनीक का उदाहरण।

अधिक उन्नत उदाहरण के लिए, बेहतर पुन: प्रयोज्यता और परीक्षण क्षमता के लिए इंटरफेसों का उपयोग करने के लिए फ़ंक्शनों को रिफैक्टर करने पर विचार करें:

**रिफैक्टरिंग से पहले:**

```go
package main

import "fmt"

type Logger struct{}

func (l Logger) Log(message string) {
    fmt.Println("Log:", message)
}

func ProcessData(data string, logger Logger) {
    // कल्पना कीजिये कि यहां कुछ डेटा प्रोसेसिंग हो रही है
    logger.Log("Data processed")
}

func main() {
    logger := Logger{}
    ProcessData("example data", logger)
}
```

**रिफैक्टरिंग के बाद:**

```go
package main

import "fmt"

type Logger interface {
    Log(message string)
}

type ConsoleLogger struct{}

func (c ConsoleLogger) Log(message string) {
    fmt.Println("Log:", message)
}

func ProcessData(data string, logger Logger) {
    // डेटा प्रोसेसिंग अपरिवर्तित रहती है
    logger.Log("Data processed")
}

func main() {
    logger := ConsoleLogger{}
    ProcessData("example data", logger)
}
```

एक इंटरफेस (`Logger`) के उपयोग में रिफैक्टरिंग, एक ठोस प्रकार (`ConsoleLogger`) की जगह, फ़ंक्शन की लचीलापन में सुधार करता है और डेटा प्रो�
