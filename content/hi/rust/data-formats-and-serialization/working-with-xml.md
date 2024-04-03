---
date: 2024-01-26 04:36:39.229744-07:00
description: "XML, \u091C\u093F\u0938\u0915\u093E \u092A\u0942\u0930\u093E \u0928\u093E\
  \u092E eXtensible Markup Language \u0939\u0948, JSON \u0915\u093E \u0935\u093F\u0938\
  \u094D\u0924\u0943\u0924 \u0938\u0902\u0938\u094D\u0915\u0930\u0923 \u091C\u0948\
  \u0938\u093E \u0939\u0948\u0964 \u091C\u092C \u0906\u092A \u092A\u0941\u0930\u093E\
  \u0928\u0947 \u0938\u093F\u0938\u094D\u091F\u092E\u094D\u0938, \u090F\u0902\u091F\
  \u0930\u092A\u094D\u0930\u093E\u0907\u091C \u0938\u0949\u092B\u094D\u091F\u0935\u0947\
  \u092F\u0930 \u092F\u093E \u0909\u0928 APIs \u0915\u0947 \u0938\u093E\u0925 \u0915\
  \u093E\u092E \u0915\u0930\u0924\u0947\u2026"
lastmod: '2024-03-13T22:44:52.004918-06:00'
model: gpt-4-0125-preview
summary: "XML, \u091C\u093F\u0938\u0915\u093E \u092A\u0942\u0930\u093E \u0928\u093E\
  \u092E eXtensible Markup Language \u0939\u0948, JSON \u0915\u093E \u0935\u093F\u0938\
  \u094D\u0924\u0943\u0924 \u0938\u0902\u0938\u094D\u0915\u0930\u0923 \u091C\u0948\
  \u0938\u093E \u0939\u0948\u0964 \u091C\u092C \u0906\u092A \u092A\u0941\u0930\u093E\
  \u0928\u0947 \u0938\u093F\u0938\u094D\u091F\u092E\u094D\u0938, \u090F\u0902\u091F\
  \u0930\u092A\u094D\u0930\u093E\u0907\u091C \u0938\u0949\u092B\u094D\u091F\u0935\u0947\
  \u092F\u0930 \u092F\u093E \u0909\u0928 APIs \u0915\u0947 \u0938\u093E\u0925 \u0915\
  \u093E\u092E \u0915\u0930\u0924\u0947 \u0939\u0948\u0902 \u091C\u093F\u0928\u094D\
  \u0939\u094B\u0902\u0928\u0947 JSON \u0915\u0940 \u0932\u0939\u0930 \u0915\u094B\
  \ \u0928\u0939\u0940\u0902 \u0905\u092A\u0928\u093E\u092F\u093E, \u0924\u094B \u0906\
  \u092A\u0915\u094B XML \u0915\u0947 \u0938\u093E\u0925 \u091C\u0942\u091D\u0928\u093E\
  \ \u092A\u0921\u093C\u0947\u0917\u093E\u0964 \u091C\u0939\u093E\u0902 XML \u0905\
  \u092A\u0928\u093E \u092E\u0939\u0924\u094D\u0935 \u0930\u0916\u0924\u093E \u0939\
  \u0948 \u0935\u0939\u093E\u0902 \u0921\u0947\u091F\u093E \u090F\u0915\u094D\u0938\
  \u091A\u0947\u0902\u091C \u0915\u0947 \u0932\u093F\u090F \u092F\u0939 \u0906\u0935\
  \u0936\u094D\u092F\u0915 \u0939\u0948\u0964."
title: "XML \u0915\u0947 \u0938\u093E\u0925 \u0915\u093E\u092E \u0915\u0930\u0928\u093E"
weight: 40
---

## कैसे:
Rust में, आप `xml-rs` जैसे crates के साथ XML को संभाल सकते हैं। इंस्टाल करने के लिए अपने `Cargo.toml` में `xml-rs = "0.8"` जोड़ें। यहां एक सरल XML को पार्स करने का तरीका है:

```rust
extern crate xml;

use xml::reader::{EventReader, XmlEvent};

fn main() {
    let xml_data = r#"<book category="fiction">
    <title>Rust in Action</title>
    <author>Tim McNamara</author>
    <year>2021</year>
</book>"#;

    let parser = EventReader::from_str(xml_data);
    for e in parser {
        match e {
            Ok(XmlEvent::StartElement { name, .. }) => {
                println!("शुरुआत: {}", name);
            }
            Ok(XmlEvent::Characters(data)) => {
                println!("टेक्स्ट: {}", data);
            }
            Ok(XmlEvent::EndElement { name }) => {
                println!("अंत: {}", name);
            }
            Err(e) => {
                println!("त्रुटि: {}", e);
            }
            _ => {}
        }
    }
}
```

आउटपुट:
```
शुरुआत: book
शुरुआत: title
टेक्स्ट: Rust in Action
अंत: title
शुरुआत: author
टेक्स्ट: Tim McNamara
अंत: author
शुरुआत: year
टेक्स्ट: 2021
अंत: year
अंत: book
```
यह कोड XML को स्ट्रीम-रीड करता है, शुरुआत और अंत तत्वों के साथ-साथ टेक्स्ट डेटा को संभालता है, प्रत्येक चरण का लॉग रखता है।

## गहराई में:
XML टेक वर्षों में एक वरिष्ठ है, जिसे 90 के दशक के अंत में वेब के लिए डिज़ाइन किया गया था। इसका डिज़ाइन पठनीयता (मशीनों और मनुष्यों दोनों के लिए) और व्यापक आत्म-वर्णनात्मक डेटा को बढ़ावा देता है।

विकल्प? ज़रूर, JSON मॉडर्न जा-टू है वेब APIs के लिए, हल्का और कम शोर। इस बीच, YAML कॉन्फ़िग्स के लिए इसके स्वच्छ लेआउट के साथ प्रशंसकों को आकर्षित कर रहा है। लेकिन XML इतनी जल्दी कहीं नहीं जा रहा है—इसके पीछे विशाल इंफ्रास्ट्रक्चर बने हुए हैं।

आंतरिक रूप से, Rust का XML पार्सिंग इटरेटर पैटर्न्स पर झुकाव रखता है, जो मेमोरी उपयोग को कम और प्रदर्शन को तेज रखता है। आपको JSON हैंडलिंग से परिचित लोगों के लिए एक वरदान के रूप में `serde-xml-rs` जैसे crates मिलेंगे।

## देखें भी:
Rust और XML पर अधिक के लिए:
- Rust के serde संगतता के लिए `serde-xml-rs`: [https://github.com/RReverser/serde-xml-rs](https://github.com/RReverser/serde-xml-rs)
- आधिकारिक Rust डॉक्यूमेंटेशन (क्योंकि ब्रश अप करना कभी बुरा नहीं होता): [https://doc.rust-lang.org/stable/book/](https://doc.rust-lang.org/stable/book/)
