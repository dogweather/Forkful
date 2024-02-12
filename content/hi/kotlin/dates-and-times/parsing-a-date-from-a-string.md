---
title:                "स्ट्रिंग से तारीख पार्स करना"
aliases:
- hi/kotlin/parsing-a-date-from-a-string.md
date:                  2024-02-03T19:15:18.289838-07:00
model:                 gpt-4-0125-preview
simple_title:         "स्ट्रिंग से तारीख पार्स करना"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/kotlin/parsing-a-date-from-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?
एक स्ट्रिंग से दिनांक पार्स करना इसका मतलब है कि पाठ को एक दिनांक वस्तु में बदलना। यह क्रिया ऐसे एप्लिकेशनों के लिए मूलभूत है जो उपयोगकर्ताओं द्वारा दर्ज की गई दिनांकों या बाहरी डेटासेट से प्राप्त दिनांकों के साथ बातचीत करते हैं, जिससे जरूरतों के अनुसार आसानी से संचालन और प्रारूपण संभव हो सकता है।

## कैसे करें:
Kotlin जावा 8 में पेश `java.time` पैकेज के माध्यम से दिनांक पार्सिंग का समर्थन करता है। यहाँ `LocalDateTime` और एक विशिष्ट पैटर्न का उपयोग करके एक सरल दृष्टिकोण है:

```kotlin
import java.time.LocalDateTime
import java.time.format.DateTimeFormatter

fun parseDateFromString(dateString: String): LocalDateTime {
    val formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss")
    return LocalDateTime.parse(dateString, formatter)
}

fun main() {
    val dateString = "2023-04-01 12:00:00"
    val date = parseDateFromString(dateString)
    println(date)  // आउटपुट: 2023-04-01T12:00
}
```

अधिक लचीलेपन के लिए, या APIs जैसे बाहरी स्त्रोतों से दिनांक संभालने के लिए, आप Joda-Time जैसी तृतीय-पक्ष लाइब्रेरी का उपयोग कर सकते हैं (हालांकि `java.time` के रूस्त रहने के साथ यह अब कम आम है)। हालांकि, JDK द्वारा प्रदान की गई आधुनिक दृष्टिकोण से चिपके रहना अधिकतर Kotlin एप्लिकेशनों के लिए पसंदीदा है।

बिना तृतीय-पक्ष लाइब्रेरीज का उपयोग किए, Kotlin में एक दिनांक को पार्स करने के लिए, आप Java 8 से पहले के संस्करणों में या Android API स्तरों में `java.time` समर्थन की कमी के लिए `SimpleDateFormat` क्लास का भी उपयोग कर सकते हैं:

```kotlin
import java.text.SimpleDateFormat

fun parseDateUsingSimpleDateFormat(dateString: String): java.util.Date {
    val formatter = SimpleDateFormat("yyyy-MM-dd HH:mm:ss")
    return formatter.parse(dateString)
}

fun main() {
    val dateString = "2023-04-01 12:00:00"
    val date = parseDateUsingSimpleDateFormat(dateString)
    println(date)  // आउटपुट आपके समय क्षेत्र के आधार पर विभिन्न होगा, उदाहरण के लिए, Sat Apr 01 12:00:00 GMT 2023
}
```

`SimpleDateFormat` के साथ काम करते समय हमेशा समय क्षेत्र सेट करना याद रखें ताकि पार्स की गई दिनांकों में अप्रत्याशित ऑफसेट से बचा जा सके।
