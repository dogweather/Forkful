---
title:                "TOML के साथ काम करना"
aliases:
- /hi/c/working-with-toml/
date:                  2024-02-03T18:13:39.399968-07:00
model:                 gpt-4-0125-preview
simple_title:         "TOML के साथ काम करना"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/c/working-with-toml.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?

TOML (टॉम की स्पष्ट, न्यूनतम भाषा) एक कॉन्फ़िगरेशन फ़ाइल प्रारूप है जिसे इसके स्पष्ट सेमांटिक्स के कारण पढ़ना आसान है। प्रोग्रामर्स इसका उपयोग एप्लिकेशन में कॉन्फ़िगरेशन फ़ाइलों के लिए करते हैं क्योंकि इसकी सादगी और मानव-पठनीयता इसे XML या JSON जैसे प्रारूपों पर कुछ संदर्भों में उत्कृष्ट विकल्प बनाती है।

## कैसे करें:

C में TOML के साथ काम करने के लिए, आपको पहले एक लाइब्रेरी की आवश्यकता होती है जो TOML फाइलों को पार्स करने में सक्षम हो, क्योंकि C स्टैंडर्ड लाइब्रेरी में यह कार्यक्षमता शामिल नहीं है। एक लोकप्रिय विकल्प `tomlc99` है, जो C99 के लिए एक हल्का TOML पार्सर है। यहां एक साधारण TOML कॉन्फ़िगरेशन फ़ाइल पढ़ने के लिए एक त्वरित मार्गदर्शिका है:

पहला, सुनिश्चित करें कि आपने `tomlc99` को इंस्टॉल किया है और आपके प्रोजेक्ट में ठीक से लिंक किया है।

**सैंपल TOML फाइल (`config.toml`):**
```toml
[database]
server = "192.168.1.1"
ports = [ 8001, 8001, 8002 ]
connection_max = 5000
enabled = true
```

**इस फाइल को पार्स करने के लिए C कोड:**

```c
#include <stdio.h>
#include <stdlib.h>
#include "toml.h"

int main() {
    FILE *configFile;
    configFile = fopen("config.toml", "r");
    if (!configFile) {
        perror("Cannot open file");
        return EXIT_FAILURE;
    }

    toml_table_t *config = toml_parse_file(configFile, NULL, 0);
    if (!config) {
        fprintf(stderr, "Error parsing file\n");
        fclose(configFile);
        return EXIT_FAILURE;
    }

    toml_table_t *database = toml_table_in(config, "database");
    if (database) {
        const char *server = toml_raw_in(database, "server");
        printf("Database Server: %s\n", server);

        toml_array_t *ports = toml_array_in(database, "ports");
        for (int i = 0; i < toml_array_nelem(ports); i++) {
            int64_t port;
            toml_int_at(ports, i, &port);
            printf("Port %d: %ld\n", i, port);
        }
    }

    toml_free(config);
    fclose(configFile);
    return EXIT_SUCCESS;
}
```

**आउटपुट:**
```
Database Server: "192.168.1.1"
Port 0: 8001
Port 1: 8001
Port 2: 8002
```

## गहराई में:

TOML को गिटहब के सह-संस्थापक टॉम प्रेस्टन-वर्नर ने अन्य कॉन्फ़िगरेशन फ़ाइल प्रारूपों में वह महसूस की गयी सीमाओं के जवाब में बनाया था। इसका उद्देश्य मनुष्यों और कंप्यूटरों दोनों के लिए सीधा और अस्पष्ट न होकर पढ़ने और लिखने में सरल होना है, बिना जटिल पार्सिंग नियमों की आवश्यकता के। C ईकोसिस्टम में, TOML Rust जैसी उच्च-स्तरीय भाषाओं में `serde_toml` या Python में `toml` की तरह पहली श्रेणी का नागरिक नहीं हो सकता है, जिनके पास नेटिव सपोर्ट के साथ लाइब्रेरियां हैं। बल्कि, C डेवलपर्स को `tomlc99` जैसी बाहरी लाइब्रेरियों पर निर्भर रहने की आवश्यकता है, लेकिन यह C के न्यूनतमवाद और प्रदर्शन पर जोर देने को देखते हुए विशिष्ट है।

जबकि TOML की स्पष्टता की प्रशंसा की जाती है, कॉन्फ़िगरेशन फ़ाइल प्रारूप चुनते समय, परियोजना की जरूरतों पर विचार करना महत्वपूर्ण है। जटिल संरचनाओं या वेब APIs के साथ इंटरेक्टिविटी की आवश्यकता वाले परिदृश्यों में, JSON या यहां तक कि YAML उनकी बढ़ी हुई जटिलता के बावजूद एक बेहतर फिट प्रदान कर सकते हैं। TOML उन कॉन्फ़िगरेशन में चमकता है जहाँ पठनीयता और सादगी सर्वोपरि होती है, न कि आवश्यकता होती है जहाँ सबसे उन्नत डेटा संरचनाएं होती हैं।
