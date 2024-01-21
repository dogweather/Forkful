---
title:                "स्ट्रिंग इंटरपोलेशन"
date:                  2024-01-20T17:51:50.582592-07:00
model:                 gpt-4-1106-preview
simple_title:         "स्ट्रिंग इंटरपोलेशन"
programming_language: "Java"
category:             "Java"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/java/interpolating-a-string.md"
---

{{< edit_this_page >}}

## What & Why? (क्या और क्यों?)
स्ट्रिंग इंटरपोलेशन यानी वेरिएबल्स और एक्सप्रेशन्स को स्ट्रिंग्स के बीच में डालना. यह हमें कोड को और पढ़ने योग्य बनाता है, जिससे डायनामिक टेक्स्ट मेसेजेस बनाना आसान हो जाता है.

## How to: (कैसे करें:)
```Java
public class StringInterpolationExample {
    public static void main(String[] args) {
        String name = "विजय";
        int age = 25;

        // Java 15 से पहले: "+" के इस्तेमाल से 
        String message = "नमस्ते, मेरा नाम है " + name + " और मैं " + age + " वर्ष का हूँ।";
        System.out.println(message);

        // Java 15 और उसके बाद: String.format का इस्तेमाल करते हुए
        String newMessage = String.format("नमस्ते, मेरा नाम है %s और मैं %d वर्ष का हूँ।", name, age);
        System.out.println(newMessage);
        
        // Java 15: Text Blocks का इस्तेमाल करते हुए (मल्टी-लाइन स्ट्रिंग्स)
        String bigMessage = """
                नमस्ते,
                मेरा नाम है %s
                और मैं %d वर्ष का हूँ।
                """.formatted(name, age);
        System.out.println(bigMessage);
    }
}
```
सैंपल आउटपुट:
```
नमस्ते, मेरा नाम है विजय और मैं 25 वर्ष का हूँ।
नमस्ते, मेरा नाम है विजय और मैं 25 वर्ष का हूँ।
नमस्ते,
मेरा नाम है विजय
और मैं 25 वर्ष का हूँ।
```

## Deep Dive (गहराई से जानकारी)
पुराने जावा वर्शंस में '+' ऑपरेटर स्ट्रिंग्स को जोड़ने के लिए ही मुख्य तरीका था. `String.format()` और `Formatter` क्लास ने फॉर्मेटेड स्ट्रिंग्स बनाने में सुधार किया. Java 15 से, टेक्स्ट ब्लॉक्स और `.formatted()` मेथड ने टेम्प्लेट्स को और भी स्पष्ट और संक्षिप्त बना दिया है.

अगर एकाधिक स्ट्रिंग्स को जोड़ना है, तो `StringBuilder` या `StringBuffer` का इस्तेमाल करना चाहिए, यह एफिशिएंसी के लिहाज से बेहतर है. स्ट्रिंग इंटरपोलेशन सीधे जावा में नहीं है, लेकिन उपर्युक्त तकनीकियाँ इसकी जरूरतों को पूरा करती हैं. 

## See Also (अधिक जानकारी)
- [Oracle's official Java documentation on String.format](https://docs.oracle.com/en/java/javase/15/docs/api/java.base/java/lang/String.html#format(java.lang.String,java.lang.Object...))
- [Text Blocks (JEP 378)](https://openjdk.java.net/jeps/378)