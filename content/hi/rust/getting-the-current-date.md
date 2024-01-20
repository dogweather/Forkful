---
title:                "वर्तमान तारीख प्राप्त करना"
html_title:           "C#: वर्तमान तारीख प्राप्त करना"
simple_title:         "वर्तमान तारीख प्राप्त करना"
programming_language: "Rust"
category:             "Rust"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/rust/getting-the-current-date.md"
---

{{< edit_this_page >}}

## क्या & क्यों? 
"करंट डेट" प्राप्त करने का मतलब है कम्प्यूटर सिस्टम में चुने गए समय को प्राप्त करना। इसे प्रोग्रामर्स निम्नलिखित कारणों से करते हैं: (1) लॉग फ़ाइलों, डेटाबेस में स्टोर डेटा, या उपयोगकर्ता की सत्र जानकारी में तारीख जोड़ने के लिए, (2) समय के बीतने का ट्रैक रखने के लिए।

## कैसे करें:
Rust में आप chrono बाइबलीयों की मदद से "करंट डेट" प्राप्त कर सकते हैं।

```Rust
use chrono::{DateTime, Local};

fn main() {
    let now: DateTime<Local> = Local::now();
    println!("{}", now);
}
```

उदाहरण कोड का आउटपुट कुछ इस प्रकार होगा:
```Rust
2022-01-19T10:23:39.761104700+05:30
```

## गहरी जानकारी:
"करंट डेट" प्राप्त करने के लिए Rust के chrono बाइबलीयों को उपयोग में लाने का विचारांध्र आधारित C++ की <ctime> बाइबलीयों से प्रेरित है।

Rust के अलावा, Python, JavaScript, और अन्य भाषाओं में भी इसे करने के समान तरीके हैं।

केवल करंट डेट प्राप्त करने के लिए नहीं, बल्कि अन्य दिनांक और समय संबंधी कार्यों के लिए भी, Rust अपनी प्रबल और विशेष तिथि-समय बाइबलीयों का उपयोग करता है। 

## देखें भी:
1. [Chrono crate](https://docs.rs/chrono/0.4.19/chrono/): Rust का समय-तारीख संग्रह 
2. [Rust date & time handling](https://stevedonovan.github.io/rustifications/2017/09/08/common-rust-lifetime-misconceptions.html) : Rust में तारीख और समय संबंधी कार्यों का उपयोग करने के तरीके 
3. [Rust official documentation](https://doc.rust-lang.org/book/): Rust का आधिकारिक डॉक्युमेंटेशन, कोडिंग उदाहरणों और गाइडलाइन्स के साथ