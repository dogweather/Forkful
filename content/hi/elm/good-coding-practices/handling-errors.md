---
date: 2024-01-26 00:51:44.266306-07:00
description: "\u090F\u0930\u0930\u094D\u0938 \u0915\u094B \u0939\u0948\u0902\u0921\
  \u0932 \u0915\u0930\u0928\u0947 \u0915\u093E \u0905\u0930\u094D\u0925 \u0939\u0948\
  \ \u0910\u0938\u093E \u0915\u094B\u0921 \u0932\u093F\u0916\u0928\u093E \u091C\u094B\
  \ \u0917\u0932\u0924\u093F\u092F\u094B\u0902 \u0915\u0940 \u092A\u094D\u0930\u0924\
  \u094D\u092F\u093E\u0936\u093E \u0915\u0930 \u0938\u0915\u0947 \u0914\u0930 \u0909\
  \u0928\u0938\u0947 \u0928\u093F\u092A\u091F \u0938\u0915\u0947\u0964 \u092A\u094D\
  \u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u0910\u0938\u093E\
  \ \u0915\u094D\u0930\u0948\u0936\u0947\u0938 \u0915\u094B \u0930\u094B\u0915\u0928\
  \u0947, \u0921\u093E\u091F\u093E \u0907\u0902\u091F\u0947\u0917\u094D\u0930\u093F\
  \u091F\u0940 \u0915\u0940 \u0930\u0915\u094D\u0937\u093E\u2026"
lastmod: '2024-03-13T22:44:52.199628-06:00'
model: gpt-4-1106-preview
summary: "\u090F\u0930\u0930\u094D\u0938 \u0915\u094B \u0939\u0948\u0902\u0921\u0932\
  \ \u0915\u0930\u0928\u0947 \u0915\u093E \u0905\u0930\u094D\u0925 \u0939\u0948 \u0910\
  \u0938\u093E \u0915\u094B\u0921 \u0932\u093F\u0916\u0928\u093E \u091C\u094B \u0917\
  \u0932\u0924\u093F\u092F\u094B\u0902 \u0915\u0940 \u092A\u094D\u0930\u0924\u094D\
  \u092F\u093E\u0936\u093E \u0915\u0930 \u0938\u0915\u0947 \u0914\u0930 \u0909\u0928\
  \u0938\u0947 \u0928\u093F\u092A\u091F \u0938\u0915\u0947\u0964 \u092A\u094D\u0930\
  \u094B\u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u0910\u0938\u093E \u0915\
  \u094D\u0930\u0948\u0936\u0947\u0938 \u0915\u094B \u0930\u094B\u0915\u0928\u0947\
  , \u0921\u093E\u091F\u093E \u0907\u0902\u091F\u0947\u0917\u094D\u0930\u093F\u091F\
  \u0940 \u0915\u0940 \u0930\u0915\u094D\u0937\u093E \u0915\u0930\u0928\u0947 \u0914\
  \u0930 \u092F\u0942\u091C\u093C\u0930\u094D\u0938 \u0915\u094B \u0915\u0943\u092A\
  \u093E\u092A\u0942\u0930\u094D\u0935\u0915 \u0935\u0948\u0915\u0932\u094D\u092A\u093F\
  \u0915 \u0938\u092E\u093E\u0927\u093E\u0928 \u092A\u094D\u0930\u0926\u093E\u0928\
  \ \u0915\u0930\u0928\u0947 \u0915\u0947 \u0932\u093F\u090F \u0915\u0930\u0924\u0947\
  \ \u0939\u0948\u0902\u0964."
title: "\u090F\u0930\u0930\u094D\u0938 \u0915\u094B \u0939\u0948\u0902\u0921\u0932\
  \ \u0915\u0930\u0928\u093E"
weight: 16
---

## कैसे करें:
Elm का मूल दर्शन है कोई रनटाइम अपवाद नहीं। इसलिए, Elm अपनी प्रकार (type) प्रणाली का उपयोग करता है, जैसे `Maybe` और `Result` प्रकारों के साथ, एरर्स को हैंडल करने के लिए।

`Maybe` परिदृश्य के लिए:

```Elm
safeDivide : Float -> Float -> Maybe Float
safeDivide numerator denominator =
    if denominator == 0 then
        Nothing
    else
        Just (numerator / denominator)
        
-- जब आप इसे चलाएंगे:

safeDivide 10 2
--> Just 5

safeDivide 10 0
--> Nothing
```

`Result` परिदृश्य के लिए:

```Elm
type Error = DivisionByZero

safeDivide : Float -> Float -> Result Error Float
safeDivide numerator denominator =
    if denominator == 0 then
        Err DivisionByZero
    else
        Ok (numerator / denominator)

-- और इसका उपयोग करते हुए:

safeDivide 10 2
--> Ok 5

safeDivide 10 0
--> Err DivisionByZero
```

## गहन अध्ययन
Elm की प्रकार प्रणाली सख्त होती है, जो समय से पहले एरर्स को पकड़ने में मदद करती है। ऐतिहासिक रूप से, अधिकांश भाषाओं ने अपवादों और रनटाइम चेक्स पर निर्भर किया था, परन्तु Elm ने संकलन-समय की गारंटियों का चयन किया। `Result` जैसे विकल्प विस्तृत एरर जानकारी देते हैं, जबकि `Maybe` हां-नहीं के परिदृश्यों के लिए सरल है। Elm की एरर हैंडलिंग प्रोग्रामर्स को सभी रास्तों पर पहले से विचार करने के लिए प्रोत्साहित करती है, भूले हुए एरर केसेस की पिटफॉल्स से बचने के लिए।

## और देखें:
- Elm की आधिकारिक गाइड का अनुभाग एरर हैंडलिंग पर: [एरर हैंडलिंग – एक परिचय](https://guide.elm-lang.org/error_handling/)
- Elm `Maybe` प्रलेखन: [Elm – Maybe](https://package.elm-lang.org/packages/elm/core/latest/Maybe)
- Elm `Result` प्रलेखन: [Elm – Result](https://package.elm-lang.org/packages/elm/core/latest/Result)
