---
title:                "जटिल संख्याओं के साथ काम करना"
date:                  2024-01-26T04:44:42.518022-07:00
model:                 gpt-4-0125-preview
simple_title:         "जटिल संख्याओं के साथ काम करना"
programming_language: "Java"
category:             "Java"
tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/java/working-with-complex-numbers.md"
---

{{< edit_this_page >}}

## क्या और क्यों?

जटिल संख्याएँ एक काल्पनिक इकाई, `i`, के जोड़ से वास्तविक संख्या की रेखा का विस्तार करती हैं, जहाँ `i^2 = -1` होता है। वे इंजीनियरिंग, भौतिकी, और उन्नत गणित जैसे क्षेत्रों में महत्वपूर्ण हैं, जहाँ वे ऐसी घटनाओं का मॉडल बनाते हैं जिन्हें वास्तविक संख्याएँ संभाल नहीं सकती, जैसे कि इलेक्ट्रिकल करंट्स और सिग्नल प्रोसेसिंग।

## कैसे करें:

जावा में जटिल संख्याओं के लिए बिल्ट-इन सपोर्ट नहीं है, लेकिन हम अपना खुद का क्लास बना सकते हैं या एक लाइब्रेरी का उपयोग कर सकते हैं। यहाँ एक सरल `ComplexNumber` क्लास बनाने और उसका उपयोग करने का एक त्वरित उदाहरण है:

```java
public class ComplexNumber {
    private double real;
    private double imaginary;

    public ComplexNumber(double real, double imaginary) {
        this.real = real;
        this.imaginary = imaginary;
    }

    public ComplexNumber add(ComplexNumber other) {
        return new ComplexNumber(this.real + other.real, this.imaginary + other.imaginary);
    }

    // ToString कॉम्प्लेक्स संख्याओं को a + bi फॉर्म में प्रदर्शित करने के लिए
    @Override
    public String toString() {
        return String.format("%.1f + %.1fi", real, imaginary);
    }

    // त्वरित परीक्षण
    public static void main(String[] args) {
        ComplexNumber c1 = new ComplexNumber(2, 3);
        ComplexNumber c2 = new ComplexNumber(1, 4);

        System.out.println("योग: " + c1.add(c2));
    }
}
```

मुख्य विधि के लिए नमूना आउटपुट होगा:

```
योग: 3.0 + 7.0i
```

## गहराई में जाना

जावा जैसी उच्च-स्तरीय भाषाओं से पहले, प्रोग्रामर सीधे फोरट्रान या सी जैसी भाषाओं में गणित पुस्तकालयों के साथ काम करते थे, जटिल संचालनों को प्रबंधित करने के लिए। यह अवधारणा 16वीं शताब्दी में वापस जाती है, गैरोलामो कार्डानो और राफेल बम्बेल्ली जैसे गणितज्ञों को श्रेय दिया जाता है।

जावा में, `java.lang.Math` आवश्यकताओं के लिए जाने का स्थान है लेकिन जटिल संख्याओं को छोड़ देता है, शायद इसलिए क्योंकि हर प्रोग्रामर उनका उपयोग नहीं करता। विकल्प? लाइब्रेरीज का उपयोग करें। Apache Commons Math `Complex` क्लास प्रदान करता है जो संचालन के लिए भिन्न विधियों से भरपूर है। यहाँ पर अपना खुद का बनाने की अच्छाई क्यों है: हल्का, आपकी सटीक जरूरतों के लिए निर्मित, और कोई लाइब्रेरी ओवरहेड नहीं।

एक महत्वपूर्ण विवरण: फ्लोटिंग-पॉइंट प्रेसिजन के लिए सावधान रहें। कंप्यूटर कुछ संख्याओं को सटीक रूप से प्रस्तुत नहीं कर सकते, जिससे गोलाई में त्रुटियाँ होती हैं। जटिल संचालनों को दोहराते समय, ये त्रुटियाँ जमा हो सकती हैं!

## और देखें

और गहरी जानकारी और जटिल संचालनों के लिए, देखें:

- [Apache Commons Math](https://commons.apache.org/proper/commons-math/)
- [JScience की Complex क्लास](http://jscience.org/)
- Oracle की ट्यूटोरियल्स [फ्लोटिंग-पॉइंट अंकगणितीय](https://docs.oracle.com/cd/E19957-01/806-3568/ncg_goldberg.html)
