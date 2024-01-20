---
title:                "नया प्रोजेक्ट शुरू करना"
html_title:           "C: नया प्रोजेक्ट शुरू करना"
simple_title:         "नया प्रोजेक्ट शुरू करना"
programming_language: "Haskell"
category:             "Haskell"
tag:                  "Getting Started"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/haskell/starting-a-new-project.md"
---

{{< edit_this_page >}}

## क्या और क्यों? : 
नया परियोजना शुरू करना मतलब किसी ताजगी अथवा विशेष उद्देश्य के साथ किसी नई कोडिंग परियोजना पर काम शुरू करना। कार्यक्रमकर्ता इसे ताजगी लाने, सीखने, और अपनी क्षमता का प्रदर्शन करने के लिए करते हैं। 

## कैसे : 
किसी नई Haskell परियोजना को शुरू करने का कोड नीचे दिया गया है, साथ ही नमूना उत्पादन। 

```Haskell 
-- एक नया मॉड्यूल बनाने का तरीका
module NewProject where

-- base मॉड्यूल लोड करना 
import Base

-- सरल फ़ंक्शन बनाना
addNumbers :: Int -> Int -> Int
addNumbers x y = x + y

-- आउटपुट देखें
main = print (addNumbers 3 5)
```
आउटपुट: 

```Haskell
8
```
## गहरा विश्लेषण :
 
इतिहास संदर्भ में, Haskell एक शुद्ध कार्यात्मक भाषा है जिसे 1990 में शुरू किया गया था। Haskell प्रोजेक्ट की स्थापना में वैगणानिक और अनुप्रयोगिक दोनों प्रकार के पहलुएँ मिलती हैं। 

विकल्पों में, अन्य कुछ stack जैसे उपकरण हैं जो हमें नए Haskell प्रोजेक्ट प्रारंभ करने में मदद कर सकते हैं। 

आगे जाते, आप सबके लिए पाठ्यक्रम का कोई मूल मॉड्यूल बनाएंगे। यहां हमने `Base` को आयात किया है, लेकिन आप इसे बदलकर किसी अन्य मॉड्यूल नाम से भी बदल सकते हैं। 

## अधिक जानकारी के लिए :
1. [Haskell शुरू करने के लिए गाइड](https://learnyouahaskell.com/chapters)
2. [Wikipedia पर Haskell](https://en.wikipedia.org/wiki/Haskell_(programming_language))