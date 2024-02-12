---
title:                "JSON के साथ काम करना"
aliases:
- hi/haskell/working-with-json.md
date:                  2024-02-03T19:23:53.704428-07:00
model:                 gpt-4-0125-preview
simple_title:         "JSON के साथ काम करना"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/haskell/working-with-json.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?
Haskell में JSON (JavaScript Object Notation) के साथ काम करना, JSON डेटा को Haskell प्रकारों में पार्सिंग करने और Haskell प्रकारों को वापस JSON में बदलने को शामिल करता है। प्रोग्रामर इसे अपने Haskell अनुप्रयोगों को वेब सेवाओं या APIs के साथ बिना किसी रुकावट के डेटा के आदान-प्रदान के लिए सक्षम करने के लिए करते हैं, जो आधुनिक सॉफ्टवेयर विकास में क्रॉस-प्लेटफॉर्म डेटा इंटरचेंज के लिए एक सामान्य अभ्यास है।

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
