---
title:                "YAML के साथ काम करना"
aliases:
- hi/go/working-with-yaml.md
date:                  2024-02-03T18:15:12.427277-07:00
model:                 gpt-4-0125-preview
simple_title:         "YAML के साथ काम करना"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/go/working-with-yaml.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?

Go में YAML के साथ काम करना YAML (YAML Ain't Markup Language) फाइलों को पार्स करना शामिल है, जो एक मानव-अनुकूल डेटा सीरियलाइजेशन मानक है, Go डेटा संरचनाओं में और इसके विपरीत। प्रोग्रामर यह काम YAML की सादगी और पठनीयता का लाभ उठाने के लिए करते हैं, जैसे कॉन्फ़िगरेशन फाइलें, एप्लिकेशन सेटिंग्स, या विभिन्न भाषाओं में लिखे गए सेवाओं और घटकों के बीच डेटा आदान-प्रदान।

## कैसे करें:

Go में YAML के साथ काम करने के लिए, आपको पहले एक लाइब्रेरी इम्पोर्ट करने की आवश्यकता होगी जो YAML पार्सिंग और सीरियलाइजेशन का समर्थन करती है, क्योंकि Go की स्टैंडर्ड लाइब्रेरी में YAML के लिए सीधा समर्थन शामिल नहीं है। इस उद्देश्य के लिए सबसे लोकप्रिय लाइब्रेरी "gopkg.in/yaml.v3" है। आरंभ करने का तरीका यहाँ दिया गया है:

1. **YAML पैकेज स्थापित करना:**

```bash
go get gopkg.in/yaml.v3
```

2. **Go स्ट्रक्चर में YAML को पार्स करना:**

सबसे पहले, Go में एक स्ट्रक्चर परिभाषित करें जो आपके YAML डेटा की संरचना के अनुरूप हो।

```go
package main

import (
  "fmt"
  "gopkg.in/yaml.v3"
  "log"
)

type Config struct {
  Database struct {
    User     string `yaml:"user"`
    Password string `yaml:"password"`
  } `yaml:"database"`
}

func main() {
  var config Config
  data := `
database:
  user: admin
  password: secret
`
  err := yaml.Unmarshal([]byte(data), &config)
  if err != nil {
    log.Fatalf("error: %v", err)
  }
  fmt.Printf("User: %s\nPassword: %s\n", config.Database.User, config.Database.Password)
}
```

**नमूना आउटपुट:**

```
User: admin
Password: secret
```

3. **एक Go स्ट्रक्चर को YAML में सीरियलाइज करना:**

यहाँ एक Go स्ट्रक्चर को वापस YAML में कैसे परिवर्तित किया जाए।

```go
package main

import (
  "fmt"
  "gopkg.in/yaml.v3"
  "log"
)

func main() {
  config := Config{
    Database: struct {
      User     string `yaml:"user"`
      Password string `yaml:"password"`
    }{
      User:     "admin",
      Password: "supersecret",
    },
  }

  data, err := yaml.Marshal(&config)
  if err != nil {
    log.Fatalf("error: %v", err)
  }
  fmt.Printf("---\n%s\n", string(data))
}
```

**नमूना आउटपुट:**

```yaml
---
database:
  user: admin
  password: supersecret
```

## गहराई से समझ:

सॉफ्टवेयर विकास में YAML का उपयोग इसके मानव-पठनीय प्रारूप के कारण बढ़ा है, जिससे यह कॉन्फ़िगरेशन फाइलों, दस्तावेज़ीकरण, या डेटा एक्सचेंज प्रारूपों के लिए एक आदर्श विकल्प बनता है। अपने समकक्ष JSON की तुलना में, YAML टिप्पणियां, स्केलर प्रकार, और संबंध सुविधाओं की पेशकश करता है, जिससे एक समृद्ध डेटा सीरियलाइजेशन फ्रेमवर्क प्रदान होता है। हालांकि, इसकी लचीलापन और सुविधाएँ पार्सिंग में जटिलता की कीमत पर आती हैं, जिससे सावधानी से निपटने पर संभावित सुरक्षा जोखिम (जैसे, मनमाने कोड निष्पादन) हो सकते हैं।

Go के लिए "gopkg.in/yaml.v3" लाइब्रेरी एक मजबूत YAML प्रोसेसिंग समाधान है, जो उपयोग में आसानी और व्यापक सुविधा समर्थन के बीच संतुलन बनाती है। वर्तमान स्थिति में, हालांकि "go-yaml/yaml" जैसे विकल्प हैं (जो "gopkg.in/yaml.v3" के पीछे की लाइब्रेरी है), चुना गया संस्करण आमतौर पर विशिष्ट परियोजना आवश्यकताओं या व्यक्तिगत पसंद पर निर्भर करता है। जब बड़े डेटा सेट या परफ़ॉर्मेंस-क्रिटिकल एप्लिकेशनों से निपटते हैं, तो प्रोग्रामर JSON जैसे सरल प्रारूपों पर विचार कर सकते हैं जिनके पार्सिंग समय और मेमोरी ओवरहेड कम होते हैं। फिर भी, कॉन्फ़िगरेशन फाइलों या सेटिंग्स के लिए जहाँ मानव पठनीयता और उपयोग में आसानी महत्वपूर्ण हैं, Go पारिस्थितिकी तंत्र में YAML एक मजबूत प्रतियोगी बना हुआ है।
