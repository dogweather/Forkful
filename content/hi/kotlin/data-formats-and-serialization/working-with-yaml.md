---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:26:57.430176-07:00
description: "YAML, \u091C\u093F\u0938\u0915\u093E \u092A\u0942\u0930\u093E \u0928\
  \u093E\u092E YAML Ain't Markup Language \u0939\u0948, \u090F\u0915 \u0909\u091A\u094D\
  \u091A \u092A\u0920\u0928\u0940\u092F \u0921\u0947\u091F\u093E \u0938\u0940\u0930\
  \u093F\u092F\u0932\u093E\u0907\u091C\u0947\u0936\u0928 \u092A\u094D\u0930\u093E\u0930\
  \u0942\u092A \u0939\u0948 \u091C\u093F\u0938\u0915\u093E \u0909\u092A\u092F\u094B\
  \u0917 \u0905\u0915\u094D\u0938\u0930 \u0915\u0949\u0928\u094D\u092B\u093C\u093F\
  \u0917\u0930\u0947\u0936\u0928 \u092B\u093C\u093E\u0907\u0932\u094B\u0902, \u0921\
  \u0947\u091F\u093E \u0938\u0902\u0917\u094D\u0930\u0939\u0923, \u0914\u0930\u2026"
lastmod: '2024-03-13T22:44:52.294081-06:00'
model: gpt-4-0125-preview
summary: "YAML, \u091C\u093F\u0938\u0915\u093E \u092A\u0942\u0930\u093E \u0928\u093E\
  \u092E YAML Ain't Markup Language \u0939\u0948, \u090F\u0915 \u0909\u091A\u094D\u091A\
  \ \u092A\u0920\u0928\u0940\u092F \u0921\u0947\u091F\u093E \u0938\u0940\u0930\u093F\
  \u092F\u0932\u093E\u0907\u091C\u0947\u0936\u0928 \u092A\u094D\u0930\u093E\u0930\u0942\
  \u092A \u0939\u0948 \u091C\u093F\u0938\u0915\u093E \u0909\u092A\u092F\u094B\u0917\
  \ \u0905\u0915\u094D\u0938\u0930 \u0915\u0949\u0928\u094D\u092B\u093C\u093F\u0917\
  \u0930\u0947\u0936\u0928 \u092B\u093C\u093E\u0907\u0932\u094B\u0902, \u0921\u0947\
  \u091F\u093E \u0938\u0902\u0917\u094D\u0930\u0939\u0923, \u0914\u0930 \u0905\u0902\
  \u0924\u0930-\u092A\u094D\u0930\u0915\u094D\u0930\u093F\u092F\u093E \u0938\u0902\
  \u0926\u0947\u0936\u0928 \u0915\u0947 \u0932\u093F\u090F \u0915\u093F\u092F\u093E\
  \ \u091C\u093E\u0924\u093E \u0939\u0948\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\
  \u0930\u093E\u092E\u0930\u094D\u0938 \u0905\u0915\u094D\u0938\u0930 \u0915\u0949\
  \u0928\u094D\u092B\u093C\u093F\u0917\u0930\u0947\u0936\u0928 \u0914\u0930 \u0938\
  \u0947\u091F\u093F\u0902\u0917\u094D\u0938 \u0915\u094B \u090F\u0915 \u0938\u0902\
  \u0930\u091A\u093F\u0924 \u092B\u093F\u0930 \u092D\u0940 \u0938\u0930\u0932 \u0924\
  \u0930\u0940\u0915\u0947 \u0938\u0947 \u092A\u094D\u0930\u092C\u0902\u0927\u093F\
  \u0924 \u0915\u0930\u0928\u0947 \u0915\u0947 \u0932\u093F\u090F YAML \u0915\u0947\
  \ \u0938\u093E\u0925 \u0915\u093E\u092E \u0915\u0930\u0924\u0947 \u0939\u0948\u0902\
  , JSON \u092F\u093E XML \u0915\u0947 \u092E\u0941\u0915\u093E\u092C\u0932\u0947\
  \ \u0909\u0938\u0915\u0940 \u0938\u094D\u092A\u0937\u094D\u091F\u0924\u093E \u0914\
  \u0930 \u0938\u093E\u0926\u0917\u0940 \u0915\u093E \u0932\u093E\u092D \u0909\u0920\
  \u093E\u0924\u0947 \u0939\u0941\u090F, \u091C\u092C \u092A\u0922\u093C\u0928\u0940\
  \u092F\u0924\u093E \u092E\u0939\u0924\u094D\u0935\u092A\u0942\u0930\u094D\u0923\
  \ \u0939\u094B\u0924\u0940 \u0939\u0948\u0964."
title: "YAML \u0915\u0947 \u0938\u093E\u0925 \u0915\u093E\u092E \u0915\u0930\u0928\
  \u093E"
weight: 41
---

## कैसे करें:
Kotlin में YAML पारंगति और सीरियलाइजेशन के लिए अंतर्निर्मित समर्थन नहीं है, लेकिन आप `snakeyaml` (सामान्य YAML पार्सिंग के लिए) और `kotlinx.serialization` (एक YAML प्रारूप एक्सटेंशन के साथ) जैसे लोकप्रिय तृतीय-पक्ष लाइब्रेरीज का उपयोग करके YAML फाइलों के साथ काम कर सकते हैं।

### `snakeyaml` का उपयोग करना
**डिपेंडेंसी:**
```kotlin
implementation 'org.yaml:snakeyaml:1.30'
```

**YAML पढ़ें:**
```kotlin
import org.yaml.snakeyaml.Yaml
import java.io.FileInputStream

fun readYaml(filePath: String) {
    val yaml = Yaml()
    val inputStream = FileInputStream(filePath)
    val data = yaml.load<Map<String, Any>>(inputStream)

    println(data)
}

// नमूना प्रयोग
fun main() {
    readYaml("config.yaml")
}
```
**नमूना `config.yaml`:**
```yaml
database:
  host: localhost
  port: 5432
```
**नमूना आउटपुट:**
```
{database={host=localhost, port=5432}}
```

### YAML के साथ `kotlinx.serialization` का उपयोग
सबसे पहले, यह सुनिश्चित करें कि आपके पास समुचित YAML समर्थन वाली `kotlinx-serialization` लाइब्रेरी है (यदि उपलब्ध है, क्योंकि `kotlinx.serialization` प्रमुखतः JSON और अन्य प्रारूपों को सीधे लक्षित करती है)।

**डिपेंडेंसी:**
```kotlin
// JSON के लिए (दृष्टांत में, YAML समर्थन या वैकल्पिक लाइब्रेरीज के लिए जाँचें)
implementation 'org.jetbrains.kotlinx:kotlinx-serialization-json:1.3.2'
```

**एक धारावाहिक डेटा क्लास निर्धारित करें:**
```kotlin
import kotlinx.serialization.Serializable

@Serializable
data class Config(
    val database: Database
)

@Serializable
data class Database(
    val host: String,
    val port: Int
)
```

दुर्भाग्यवश, लेखन के समय, `kotlinx.serialization` में सीधे YAML समर्थन सीमित या विकसित हो सकता है। आपको एक मध्यवर्ती प्रतिनिधित्व (जैसे कि `snakeyaml` के साथ YAML को JSON में परिवर्तित करना और फिर `kotlinx.serialization` के साथ JSON का पार्सिंग करना) का उपयोग करने की आवश्यकता पड़ सकती है या `kotlinx.serialization` के साथ संगत समुदाय संचालित YAML सीरियलाइजेशन प्रोजेक्ट्स की तलाश करनी पड़ सकती है।

JSON के लिए, कोड कुछ इस तरह दिखेगा:
```kotlin
import kotlinx.serialization.json.Json
import kotlinx.serialization.decodeFromString

fun main() {
    val jsonText = """
    {
        "database": {
            "host": "localhost",
            "port": 5432
        }
    }
    """.trimIndent()
    
    val config = Json.decodeFromString<Config>(jsonText)
    println(config)
}
```

क्योंकि Kotlin और इसका पारिस्थितिक तंत्र लगातार विकसित हो रहा है, YAML समर्थन और लाइब्रेरियों के लिए नवीनतम जानकारी के लिए आधिकारिक दस्तावेज़ीकरण और समुदाय संसाधनों पर नज़र रखें।
