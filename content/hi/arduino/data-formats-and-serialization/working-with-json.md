---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:22:37.526257-07:00
description: "JSON, \u092F\u093E JavaScript Object Notation, \u090F\u0915 \u0939\u0932\
  \u094D\u0915\u093E \u0921\u0947\u091F\u093E \u0907\u0902\u091F\u0930\u091A\u0947\
  \u0902\u091C \u092B\u0949\u0930\u094D\u092E\u0947\u091F \u0939\u0948, \u091C\u094B\
  \ \u0907\u0938\u0947 Arduino \u092A\u094D\u0930\u094B\u091C\u0947\u0915\u094D\u091F\
  \u094D\u0938 \u092E\u0947\u0902 \u0921\u0947\u091F\u093E \u0938\u0902\u0917\u094D\
  \u0930\u0939\u0923 \u092F\u093E \u0915\u0949\u0928\u094D\u092B\u093C\u093F\u0917\
  \u0930\u0947\u0936\u0928 \u092B\u093E\u0907\u0932\u094B\u0902 \u0915\u0947 \u0932\
  \u093F\u090F \u0906\u0926\u0930\u094D\u0936\u2026"
lastmod: '2024-03-13T22:44:52.810805-06:00'
model: gpt-4-0125-preview
summary: "JSON, \u092F\u093E JavaScript Object Notation, \u090F\u0915 \u0939\u0932\
  \u094D\u0915\u093E \u0921\u0947\u091F\u093E \u0907\u0902\u091F\u0930\u091A\u0947\
  \u0902\u091C \u092B\u0949\u0930\u094D\u092E\u0947\u091F \u0939\u0948, \u091C\u094B\
  \ \u0907\u0938\u0947 Arduino \u092A\u094D\u0930\u094B\u091C\u0947\u0915\u094D\u091F\
  \u094D\u0938 \u092E\u0947\u0902 \u0921\u0947\u091F\u093E \u0938\u0902\u0917\u094D\
  \u0930\u0939\u0923 \u092F\u093E \u0915\u0949\u0928\u094D\u092B\u093C\u093F\u0917\
  \u0930\u0947\u0936\u0928 \u092B\u093E\u0907\u0932\u094B\u0902 \u0915\u0947 \u0932\
  \u093F\u090F \u0906\u0926\u0930\u094D\u0936 \u092C\u0928\u093E\u0924\u093E \u0939\
  \u0948\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930 \u0907\
  \u0938\u0947 \u0907\u0938\u0915\u0940 \u0938\u093E\u0926\u0917\u0940 \u0914\u0930\
  \ \u0935\u093F\u092D\u093F\u0928\u094D\u0928 \u092A\u094D\u0930\u094B\u0917\u094D\
  \u0930\u093E\u092E\u093F\u0902\u0917 \u0935\u093E\u0924\u093E\u0935\u0930\u0923\u094B\
  \u0902 \u092E\u0947\u0902 \u092A\u0920\u0928\u0940\u092F\u0924\u093E \u0915\u0947\
  \ \u0915\u093E\u0930\u0923 \u0909\u092A\u092F\u094B\u0917 \u0915\u0930\u0924\u0947\
  \ \u0939\u0948\u0902, \u091C\u093F\u0938\u092E\u0947\u0902 Arduino \u0936\u093E\u092E\
  \u093F\u0932 \u0939\u0948, \u091C\u094B \u0935\u0947\u092C APIs \u092F\u093E \u0905\
  \u0928\u094D\u092F \u0938\u093F\u0938\u094D\u091F\u092E\u094B\u0902 \u0915\u0947\
  \ \u0938\u093E\u0925 \u0938\u0939\u091C \u0921\u0947\u091F\u093E \u0907\u0902\u091F\
  \u0930\u091A\u0947\u0902\u091C \u0915\u094B \u0938\u0915\u094D\u0937\u092E \u092C\
  \u0928\u093E\u0924\u093E \u0939\u0948\u0964."
title: "JSON \u0915\u0947 \u0938\u093E\u0925 \u0915\u093E\u092E \u0915\u0930\u0928\
  \u093E"
weight: 38
---

## कैसे:
Arduino में JSON के साथ कार्य करने के लिए, `ArduinoJson` लाइब्रेरी इसके उपयोग की सहजता और दक्षता के कारण एक लोकप्रिय विकल्प है। यह JSON स्ट्रिंग्स को पार्स करने, उनमें संशोधन करने, और वस्तुओं को वापस JSON स्ट्रिंग्स में सिरियलाइज़ करने की अनुमति देता है। इसका उपयोग कैसे करें, निम्न है:

1. **ArduinoJson लाइब्रेरी को इंस्टॉल करें**: Arduino IDE में लाइब्रेरी मैनेजर का उपयोग करें और "ArduinoJson" को इंस्टॉल करें।

2. **एक JSON स्ट्रिंग को डिसेरियलाइज करें**: यहाँ बताया गया है कि कैसे एक JSON स्ट्रिंग को पार्स किया जाए और मूल्यों को निकाला जाए।

```cpp
#include <ArduinoJson.h>

const char* json = "{\"sensor\":\"gps\",\"time\":1351824120,\"data\":[48.756080,2.302038]}";

void setup() {
  Serial.begin(9600);
  StaticJsonDocument<200> doc; // JSON दस्तावेज़ के अनुसार आकार समायोजित करें
  DeserializationError error = deserializeJson(doc, json);

  if (error) {
    Serial.print(F("deserializeJson() failed: "));
    Serial.println(error.f_str());
    return;
  }

  const char* sensor = doc["sensor"]; // "gps"
  long time = doc["time"]; // 1351824120
  float latitude = doc["data"][0]; // 48.756080
  float longitude = doc["data"][1]; // 2.302038
  
  Serial.println(sensor);
  Serial.println(time);
  Serial.println(latitude, 6);
  Serial.println(longitude, 6);
}

void loop() {
  // खाली loop
}
```

नमूना आउटपुट:

```
gps
1351824120
48.756080
2.302038
```

3. **एक JSON स्ट्रिंग में सिरियलाइज करें**: यहाँ बताया गया है कि कैसे डेटा से एक JSON स्ट्रिंग बनाई जाए।

```cpp
#include <ArduinoJson.h>

void setup() {
  Serial.begin(9600);

  StaticJsonDocument<200> doc; // डेटा के अनुसार आकार समायोजित करें
  doc["sensor"] = "gps";
  doc["time"] = 1351824120;
  JsonArray data = doc.createNestedArray("data");
  data.add(48.756080);
  data.add(2.302038);

  serializeJson(doc, Serial);
}

void loop() {
  // खाली loop
}
```

नमूना आउटपुट (पढ़ने के लिए स्वरूपित):

```
{"sensor":"gps","time":1351824120,"data":[48.756080,2.302038]}
```

`ArduinoJson` लाइब्रेरी का प्रभावी उपयोग Arduino प्रोजेक्ट्स को एक मानव-पठनीय प्रारूप में जटिल डेटा संरचनाओं को संवाद करने की अनुमति देता है, वेब सेवाओं के साथ विकास और एकीकरण को सुविधाजनक बनाता है।
