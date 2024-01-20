---
title:                "एक पाठ फ़ाइल पढ़ना"
html_title:           "Bash: एक पाठ फ़ाइल पढ़ना"
simple_title:         "एक पाठ फ़ाइल पढ़ना"
programming_language: "Gleam"
category:             "Gleam"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/gleam/reading-a-text-file.md"
---

{{< edit_this_page >}}

## क्या और क्यों?

एक पाठ फ़ाइल को पढ़ना मतलब फ़ाइल से डेटा प्राप्त करना। प्रोग्रामर इसे डेटा को संसाधित व परिवर्तित करने के लिए करते हैं।

## कैसे करें:

यहां हम एक टेक्स्ट फ़ाइल कैसे पढ़ें, इसकी कोडिंग उदाहरण देते हैं:
```Gleam
import gleam/otp/filesystem.{read}

fn main() {
  let path = "example.txt" // आपकी फ़ाइल का पथ यहां
  case read(path) {
    Ok(file_content) -> io.println(file_content)
    Error(e) -> io.println("फ़ाइल पढ़ने में त्रुटि: ", e)
  }
}
```
इस कोड का उदाहरण रखते हैं कि यदि आपकी फ़ाइल "example.txt" कुछ ऐसा दिखती है: `"हेल्लो वर्ल्ड!"`, तो आउटपुट होगा: `हेल्लो वर्ल्ड!`.

## गहराई में जानें

हिस्टोरिकल संदर्भ: पाठ फ़ाइलों को पढ़ने की आवश्यकता कंप्यूटर प्रोग्रामिंग के आरंभ से ही रही है। इसे डेटा को आवश्यकता अनुसार परिवर्तित करने के लिए किया जाता है।

विकल्प: आप फ़ाइलों को पढ़ने के लिए अन्य भाषाओं जैसे कि Python, Java, Javascript आदि का उपयोग कर सकते हैं। हालांकि, हर भाषा की अपनी खुद की विशेषताएं और संरचना होती है।

व्याख्यानिक विवरण: Gleam फ़ाइलों का उपयोग करने में बहुत सरल है। `gleam/otp/filesystem.{read}` इम्पोर्ट करके, `read()` फ़ंक्शन के साथ आप किसी भी फ़ाइल को पढ़ सकते हैं। यदि कोई त्रुटि होती है, तो यह त्रुटि को प्रकाशित करेगा।

## अधिक देखें

अगर आप और जानकारी चाहते हैं, तो निम्नलिखित लिंक्स देखें:

1. [Gleam का विश्लेषण](https://gleam.run/tour/)
2. [Gleam के रिपॉजिटरी](https://github.com/gleam-lang/gleam)
3. [फ़ाइल IO के बारे में](https://gleam.run/book/tour/filesystem.html)