---
title:                "बेसिक प्रमाणीकरण के साथ HTTP अनुरोध भेजना"
date:                  2024-01-20T18:02:14.373941-07:00
model:                 gpt-4-1106-preview
simple_title:         "बेसिक प्रमाणीकरण के साथ HTTP अनुरोध भेजना"
programming_language: "Kotlin"
category:             "Kotlin"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/kotlin/sending-an-http-request-with-basic-authentication.md"
---

{{< edit_this_page >}}

## क्या और क्यों?
HTTP request भेजना एक वेब सर्वर से डेटा माँगना है। Basic authentication का उपयोग करके, हम सर्वर को username और password भेजकर अपनी पहचान साबित करते हैं। प्रोग्रामर्स सुरक्षित एपीआई या रिसोर्सेज से डेटा पाने के लिए इस प्रक्रिया का उपयोग करते हैं।

## कैसे करें:
```Kotlin
import java.net.Authenticator
import java.net.PasswordAuthentication
import java.net.URL
import javax.net.ssl.HttpsURLConnection

fun main() {
    val url = URL("https://your-api-endpoint.com/data")
    Authenticator.setDefault(object : Authenticator() {
        override fun getPasswordAuthentication(): PasswordAuthentication {
            return PasswordAuthentication("username", "password".toCharArray())
        }
    })

    with(url.openConnection() as HttpsURLConnection) {
        requestMethod = "GET"

        println("\nSending 'GET' request to URL : $url")
        println("Response Code : $responseCode")
        inputStream.bufferedReader().use {
            it.lines().forEach { line -> println(line) }
        }
    }
}
```
इस कोड में, हम URL और Basic authentication सेट कर रहे हैं और response को प्रिंट कर रहे हैं।

## गहराई से जानकारी:
Basic authentication एक HTTP authentication protocol है जिसमें username और password Base64 में encode करके HTTP header में भेजे जाते हैं। यह सरल और व्यापक रूप से समर्थित है, लेकिन इसकी सुरक्षा कमजोर मानी जाती है क्योंकि अगर ट्रैफ़िक को इंटरसेप्ट किया जाता है, तो क्रेडेंशल्स चोरी हो सकते हैं। इसी कारण इसे HTTPS के साथ इस्तेमाल करना चाहिए।

वैकल्पिक तौर पर, OAuth, टोकन बेस्ड authentication, और API keys जैसे ज़्यादा सुरक्षित मार्ग भी हैं। Basic authentication का इस्तेमाल अब भी निजी या न के बराबर सुरक्षा जरूरत वाले एपीआईज के लिए किया जाता है।

इम्प्लीमेंटेशन की बात करें तो, `Authenticator` का उपयोग ग्लोबल डिफ़ॉल्ट authentication को सेट करने के लिए किया जाता है। `HttpsURLConnection` का इस्तेमाल HTTP methods को निर्धारित करने और सर्वर से प्रतिक्रिया पाने के लिए किया जाता है। 

## संबंधित सूत्र:
- [कोटलिन आधिकारिक डॉक्यूमेंटेशन](https://kotlinlang.org/docs/home.html)
- [RFC 7617, The 'Basic' HTTP Authentication Scheme](https://tools.ietf.org/html/rfc7617)
- [OKHTTP, एक लोकप्रिय HTTP & HTTP/2 client के लिए Kotlin/Java लाइब्रेरी](https://square.github.io/okhttp/)
- [वेब सेवाओं के लिए Spring Security](https://spring.io/guides/topicals/spring-security-architecture)
