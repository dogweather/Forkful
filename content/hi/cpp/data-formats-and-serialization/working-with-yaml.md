---
aliases:
- /hi/cpp/working-with-yaml/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:25:22.097446-07:00
description: "YAML, \u091C\u093F\u0938\u0915\u093E \u092A\u0942\u0930\u093E \u0928\
  \u093E\u092E YAML Ain't Markup Language \u0939\u0948, \u090F\u0915 \u092E\u093E\u0928\
  \u0935-\u092A\u0920\u0928\u0940\u092F \u0921\u0947\u091F\u093E \u0938\u0940\u0930\
  \u093F\u092F\u0932\u093E\u0907\u091C\u0947\u0936\u0928 \u092A\u094D\u0930\u093E\u0930\
  \u0942\u092A \u0939\u0948\u0964 \u0915\u093E\u0930\u094D\u092F\u0915\u094D\u0930\
  \u092E\u0915\u0930\u094D\u0924\u093E \u0907\u0938\u0915\u093E \u0909\u092A\u092F\
  \u094B\u0917 \u0915\u0949\u0928\u094D\u092B\u093F\u0917\u0930\u0947\u0936\u0928\
  \ \u092B\u093E\u0907\u0932\u094B\u0902, \u0921\u0947\u091F\u093E \u0921\u0902\u092A\
  \u093F\u0902\u0917,\u2026"
lastmod: 2024-02-18 23:09:03.927230
model: gpt-4-0125-preview
summary: "YAML, \u091C\u093F\u0938\u0915\u093E \u092A\u0942\u0930\u093E \u0928\u093E\
  \u092E YAML Ain't Markup Language \u0939\u0948, \u090F\u0915 \u092E\u093E\u0928\u0935\
  -\u092A\u0920\u0928\u0940\u092F \u0921\u0947\u091F\u093E \u0938\u0940\u0930\u093F\
  \u092F\u0932\u093E\u0907\u091C\u0947\u0936\u0928 \u092A\u094D\u0930\u093E\u0930\u0942\
  \u092A \u0939\u0948\u0964 \u0915\u093E\u0930\u094D\u092F\u0915\u094D\u0930\u092E\
  \u0915\u0930\u094D\u0924\u093E \u0907\u0938\u0915\u093E \u0909\u092A\u092F\u094B\
  \u0917 \u0915\u0949\u0928\u094D\u092B\u093F\u0917\u0930\u0947\u0936\u0928 \u092B\
  \u093E\u0907\u0932\u094B\u0902, \u0921\u0947\u091F\u093E \u0921\u0902\u092A\u093F\
  \u0902\u0917,\u2026"
title: "YAML \u0915\u0947 \u0938\u093E\u0925 \u0915\u093E\u092E \u0915\u0930\u0928\
  \u093E"
---

{{< edit_this_page >}}

## क्या और क्यों?

YAML, जिसका पूरा नाम YAML Ain't Markup Language है, एक मानव-पठनीय डेटा सीरियलाइजेशन प्रारूप है। कार्यक्रमकर्ता इसका उपयोग कॉन्फिगरेशन फाइलों, डेटा डंपिंग, और पढ़ने में आसान और समझने में सरल सिंटैक्स के कारण XML या JSON की तुलना में संरचनागत डेटा स्टोर करने के लिए इसका उपयोग करते हैं।

## कैसे करें:

C++ में YAML के साथ काम करने के लिए लोकप्रिय पसंद `yaml-cpp` लाइब्रेरी है। सबसे पहले, सुनिश्चित करें कि आपके पास `yaml-cpp` स्थापित है और आपके C++ प्रोजेक्ट के साथ सही ढंग से लिंक किया गया है।

**एक YAML फाइल पढ़ना:**

```cpp
#include <iostream>
#include <fstream>
#include <yaml-cpp/yaml.h>

int main() {
    YAML::Node config = YAML::LoadFile("config.yaml");
    
    if(config["title"]) {
        std::cout << "शीर्षक: " << config["title"].as<std::string>() << std::endl;
    }
    
    return 0;
}
```

एक `config.yaml` जो इस तरह दिखती है:

```yaml
title: "उदाहरण YAML"
```

उपरोक्त C++ कोड चलाने पे प्रोड्यूस होगा:

```
शीर्षक: उदाहरण YAML
```

**एक YAML फाइल में लिखना:**

```cpp
#include <fstream>
#include <yaml-cpp/yaml.h>

int main() {
    YAML::Emitter out;
    out << YAML::BeginMap;
    out << YAML::Key << "शीर्षक" << YAML::Value << "उदाहरण YAML";
    out << YAML::EndMap;
    
    std::ofstream fout("output.yaml");
    fout << out.c_str();
    
    return 0;
}
```

यह कोड एक `output.yaml` बनाएगा जिसमें सामग्री होगी:

```yaml
title: उदाहरण YAML
```

ये उदाहरण C++ का उपयोग करके YAML फाइलों से पढ़ने और लिखने के बुनियादी परिचय के तौर पर काम करते हैं `yaml-cpp` लाइब्रेरी का उपयोग करके। अधिक जटिल संरचनाओं और उपयोग के मामलों के लिए, कृपया `yaml-cpp` डॉक्यूमेंटेशन को देखें जिसमें सीक्वेंसेस, टैग्स, और अधिक उन्नत सीरियलाइजेशन और डीसीरियलाइजेशन तकनीकों जैसी विशेषताओं का पता चलता है।
