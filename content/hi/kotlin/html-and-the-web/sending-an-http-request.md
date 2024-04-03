---
date: 2024-01-20 18:00:33.756561-07:00
description: "HTTP \u0905\u0928\u0941\u0930\u094B\u0927 \u092D\u0947\u091C\u0928\u0947\
  \ \u0915\u093E \u092E\u0924\u0932\u092C \u0939\u0948 \u0935\u0947\u092C \u0938\u0930\
  \u094D\u0935\u0930 \u0938\u0947 \u091C\u093E\u0928\u0915\u093E\u0930\u0940 \u092E\
  \u093E\u0902\u0917\u0928\u093E \u092F\u093E \u0909\u0938\u0947 \u0921\u0947\u091F\
  \u093E \u092D\u0947\u091C\u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\
  \u0930\u093E\u092E\u0930\u094D\u0938 \u0910\u0938\u093E \u0924\u092C \u0915\u0930\
  \u0924\u0947 \u0939\u0948\u0902 \u091C\u092C \u0909\u0928\u0915\u0947 \u090F\u092A\
  \u094D\u0932\u093F\u0915\u0947\u0936\u0928 \u0915\u094B \u0907\u0902\u091F\u0930\
  \u0928\u0947\u091F \u092A\u0930 \u0921\u0947\u091F\u093E \u090F\u0915\u094D\u0938\
  \u0947\u0938 \u0915\u0930\u0928\u093E\u2026"
lastmod: '2024-03-13T22:44:52.253527-06:00'
model: gpt-4-1106-preview
summary: "HTTP \u0905\u0928\u0941\u0930\u094B\u0927 \u092D\u0947\u091C\u0928\u0947\
  \ \u0915\u093E \u092E\u0924\u0932\u092C \u0939\u0948 \u0935\u0947\u092C \u0938\u0930\
  \u094D\u0935\u0930 \u0938\u0947 \u091C\u093E\u0928\u0915\u093E\u0930\u0940 \u092E\
  \u093E\u0902\u0917\u0928\u093E \u092F\u093E \u0909\u0938\u0947 \u0921\u0947\u091F\
  \u093E \u092D\u0947\u091C\u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\
  \u0930\u093E\u092E\u0930\u094D\u0938 \u0910\u0938\u093E \u0924\u092C \u0915\u0930\
  \u0924\u0947 \u0939\u0948\u0902 \u091C\u092C \u0909\u0928\u0915\u0947 \u090F\u092A\
  \u094D\u0932\u093F\u0915\u0947\u0936\u0928 \u0915\u094B \u0907\u0902\u091F\u0930\
  \u0928\u0947\u091F \u092A\u0930 \u0921\u0947\u091F\u093E \u090F\u0915\u094D\u0938\
  \u0947\u0938 \u0915\u0930\u0928\u093E \u0939\u094B\u0924\u093E \u0939\u0948 \u092F\
  \u093E \u0936\u0947\u092F\u0930 \u0915\u0930\u0928\u093E \u0939\u094B\u0924\u093E\
  \ \u0939\u0948\u0964."
title: "HTTP \u0905\u0928\u0941\u0930\u094B\u0927 \u092D\u0947\u091C\u0928\u093E"
weight: 44
---

## कैसे करें:
```Kotlin
import java.net.HttpURLConnection
import java.net.URL

fun main() {
    val url = URL("http://example.com") // अपना URL डालें
    with(url.openConnection() as HttpURLConnection) {
        requestMethod = "GET"  // या "POST", "PUT", "DELETE", आदि
        
        println("Response Code: $responseCode")
        inputStream.bufferedReader().use {
            it.lines().forEach { line ->
                println(line)
            }
        }
    }
}
```
सैंपल आउटपुट:
```
Response Code: 200
<!doctype html>
<html>
<head>
...
</head>
<body>
...
</body>
</html>
```

## गहराई में:
HTTP अनुरोध भेजना इंटरनेट के माध्यम से संवाद करने का एक मौलिक तरीका है जिसे 1990 के दशक से प्रयोग किया जा रहा है। जहां Java में `HttpURLConnection` उपयोग किया जाता था, वहीं Kotlin में हम इसे अधिक सरलता से कर सकते हैं और बेहतर सिंटैक्स के साथ। कुछ विकल्पों में लाइब्रेरीज जैसे कि OkHttp, Retrofit, या Ktor होती हैं, जो और अधिक सुविधाजनक एपीआई प्रदान करती हैं और जटिलताओं को सरल बनाती हैं। इन्हें उपयोग करते हुए आप प्राप्ती, परिचीती, और प्रबंधन को बेहतर तरीके से संचालित कर सकते हैं।

## इसे भी देखें:
- [OkHttp GitHub Repository](https://github.com/square/okhttp)
- [Kotlin के लिए Ktor](https://ktor.io/)
- [Retrofit GitHub Repository](https://github.com/square/retrofit)

नोट: जिन भारतीय पाठकों के लिए यह आर्टिकल लिखा गया है, वे ऊपर दिए गए लिंक्स पर जाकर कोडिंग में इस्तेमाल होने वाली लाइब्रेरीज के बारे में और जान सकते हैं।
