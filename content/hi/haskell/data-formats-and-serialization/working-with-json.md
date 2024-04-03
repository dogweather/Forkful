---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:23:53.704428-07:00
description: "Haskell \u092E\u0947\u0902 JSON (JavaScript Object Notation) \u0915\u0947\
  \ \u0938\u093E\u0925 \u0915\u093E\u092E \u0915\u0930\u0928\u093E, JSON \u0921\u0947\
  \u091F\u093E \u0915\u094B Haskell \u092A\u094D\u0930\u0915\u093E\u0930\u094B\u0902\
  \ \u092E\u0947\u0902 \u092A\u093E\u0930\u094D\u0938\u093F\u0902\u0917 \u0915\u0930\
  \u0928\u0947 \u0914\u0930 Haskell \u092A\u094D\u0930\u0915\u093E\u0930\u094B\u0902\
  \ \u0915\u094B \u0935\u093E\u092A\u0938 JSON \u092E\u0947\u0902 \u092C\u0926\u0932\
  \u0928\u0947\u2026"
lastmod: '2024-03-13T22:44:52.441426-06:00'
model: gpt-4-0125-preview
summary: "Haskell \u092E\u0947\u0902 JSON (JavaScript Object Notation) \u0915\u0947\
  \ \u0938\u093E\u0925 \u0915\u093E\u092E \u0915\u0930\u0928\u093E, JSON \u0921\u0947\
  \u091F\u093E \u0915\u094B Haskell \u092A\u094D\u0930\u0915\u093E\u0930\u094B\u0902\
  \ \u092E\u0947\u0902 \u092A\u093E\u0930\u094D\u0938\u093F\u0902\u0917 \u0915\u0930\
  \u0928\u0947 \u0914\u0930 Haskell \u092A\u094D\u0930\u0915\u093E\u0930\u094B\u0902\
  \ \u0915\u094B \u0935\u093E\u092A\u0938 JSON \u092E\u0947\u0902 \u092C\u0926\u0932\
  \u0928\u0947 \u0915\u094B \u0936\u093E\u092E\u093F\u0932 \u0915\u0930\u0924\u093E\
  \ \u0939\u0948\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\
  \ \u0907\u0938\u0947 \u0905\u092A\u0928\u0947 Haskell \u0905\u0928\u0941\u092A\u094D\
  \u0930\u092F\u094B\u0917\u094B\u0902 \u0915\u094B \u0935\u0947\u092C \u0938\u0947\
  \u0935\u093E\u0913\u0902 \u092F\u093E APIs \u0915\u0947 \u0938\u093E\u0925 \u092C\
  \u093F\u0928\u093E \u0915\u093F\u0938\u0940 \u0930\u0941\u0915\u093E\u0935\u091F\
  \ \u0915\u0947 \u0921\u0947\u091F\u093E \u0915\u0947 \u0906\u0926\u093E\u0928-\u092A\
  \u094D\u0930\u0926\u093E\u0928 \u0915\u0947 \u0932\u093F\u090F \u0938\u0915\u094D\
  \u0937\u092E \u0915\u0930\u0928\u0947 \u0915\u0947 \u0932\u093F\u090F \u0915\u0930\
  \u0924\u0947 \u0939\u0948\u0902, \u091C\u094B \u0906\u0927\u0941\u0928\u093F\u0915\
  \ \u0938\u0949\u092B\u094D\u091F\u0935\u0947\u092F\u0930 \u0935\u093F\u0915\u093E\
  \u0938 \u092E\u0947\u0902 \u0915\u094D\u0930\u0949\u0938-\u092A\u094D\u0932\u0947\
  \u091F\u092B\u0949\u0930\u094D\u092E \u0921\u0947\u091F\u093E \u0907\u0902\u091F\
  \u0930\u091A\u0947\u0902\u091C \u0915\u0947 \u0932\u093F\u090F \u090F\u0915 \u0938\
  \u093E\u092E\u093E\u0928\u094D\u092F \u0905\u092D\u094D\u092F\u093E\u0938 \u0939\
  \u0948\u0964."
title: "JSON \u0915\u0947 \u0938\u093E\u0925 \u0915\u093E\u092E \u0915\u0930\u0928\
  \u093E"
weight: 38
---

## कैसे:
Haskell में JavaScript की तरह JSON के लिए अंतर्निर्मित समर्थन नहीं होता, लेकिन **Aeson** जैसी तृतीय-पक्ष पुस्तकालयों की मदद से, JSON के साथ कार्य करना सीधा हो जाता है। Aeson एन्कोडिंग (Haskell मूल्यों को JSON में बदलने) और डिकोडिंग (JSON को Haskell मूल्यों में पार्सिंग करने) के लिए उच्च-स्तरीय और निम्न-स्तरीय दोनों कार्य प्रदान करता है।

### Aeson को इंस्टॉल करना
पहले, अपनी प्रोजेक्ट की निर्भरता में Aeson को जोड़ें, अपनी `.cabal` फाइल को अपडेट करके या Stack या Cabal का प्रत्यक्ष उपयोग करके:

```shell
cabal update && cabal install aeson
```
या, अगर आप Stack का उपयोग कर रहे हैं:
```shell
stack install aeson
```

### JSON पार्सिंग
चलिए JSON डेटा को Haskell प्रकार में डिकोड करने का एक बुनियादी उदाहरण से शुरू करते हैं। मान लीजिए हमारे पास एक व्यक्ति को दर्शाने वाला निम्न JSON है:

```json
{
  "name": "John Doe",
  "age": 30
}
```

पहले, एक संबंधित Haskell डेटा प्रकार को परिभाषित करें और इसे `FromJSON` का एक उदाहरण बनाएँ:

```haskell
{-# LANGUAGE DeriveGeneric #-}

import GHC.Generics (Generic)
import Data.Aeson (FromJSON, decode)
import qualified Data.ByteString.Lazy as B

data Person = Person
  { name :: String
  , age  :: Int
  } deriving (Generic, Show)

instance FromJSON Person

-- एक फाइल से JSON को डिकोड करने वाला फंक्शन
decodePerson :: FilePath -> IO (Maybe Person)
decodePerson filePath = do
  personJson <- B.readFile filePath
  return $ decode personJson
```
उपयोग:
माना `person.json` में ऊपर दिखाए गए JSON डेटा है, चलाएँ:
```haskell
main :: IO ()
main = do
  maybePerson <- decodePerson "person.json"
  print maybePerson
```
नमूना आउटपुट:
```haskell
Just (Person {name = "John Doe", age = 30})
```

### Haskell मूल्यों को JSON के रूप में एन्कोडिंग
एक Haskell मूल्य को वापस JSON में बदलने के लिए, आपको अपने प्रकार को `ToJSON` का एक उदाहरण बनाना होगा और फिर `encode` का उपयोग करें।

```haskell
import Data.Aeson (ToJSON, encode)
import GHC.Generics (Generic)

-- मान लीजिए पहले से मौजूद Person प्रकार

instance ToJSON Person

encodePerson :: Person -> B.ByteString
encodePerson = encode

main :: IO ()
main = do
  let person = Person "Jane Doe" 32
  putStrLn $ show $ encodePerson person
```
नमूना आउटपुट:
```json
{"name":"Jane Doe","age":32}
```

ये उदाहरण Aeson का उपयोग करके Haskell में JSON के साथ काम करने की मूल बातों को दर्शाते हैं। याद रखें, Aeson बहुत अधिक प्रदान करता है, जिसमें कस्टम पार्सिंग नियम, जटिल नेस्टेड JSON के साथ कार्य करना, और बहुत कुछ शामिल है, जो विभिन्न जरूरतों और परिदृश्यों के लिए उपयुक्त है।
