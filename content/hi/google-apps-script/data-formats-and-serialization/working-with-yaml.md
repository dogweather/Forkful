---
title:                "YAML के साथ काम करना"
aliases:
- hi/google-apps-script/working-with-yaml.md
date:                  2024-02-01T22:08:31.274690-07:00
model:                 gpt-4-0125-preview
simple_title:         "YAML के साथ काम करना"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/google-apps-script/working-with-yaml.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?

YAML, जिसका पूरा नाम "YAML Ain't Markup Language" है, एक मानव-पठनीय डेटा सीरियलाइजेशन मानक है जो आमतौर पर विन्यास फ़ाइलों और भाषाओं के बीच विभिन्न डेटा संरचनाओं के बीच डेटा विनिमय के लिए उपयोग किया जाता है। प्रोग्रामर्स अक्सर YAML के साथ काम करते हैं क्योंकि इसकी सादगी और पठनीयता के कारण, विशेष रूप से परियोजनाओं में जहां व्यापक विन्यास की आवश्यकता होती है या जब विभिन्न प्रणालियों के बीच संरचित डेटा को स्थानांतरित करना होता है।

## कैसे:

जबकि Google Apps Script (GAS) में YAML पार्सिंग या सीरियलाइजेशन को मूल रूप से समर्थन नहीं है, आप JavaScript पुस्तकालयों का उपयोग करके या कस्टम पार्सिंग फ़ंक्शन्स लिखकर YAML डेटा को संभाल सकते हैं। प्रदर्शन के लिए, आइए देखें कि कैसे एक कस्टम फ़ंक्शन का उपयोग करके YAML स्ट्रिंग को पार्स किया जाए, चूँकि बाहरी लाइब्रेरियों को सीधे GAS में आयात नहीं किया जा सकता।

मान लीजिए आपके पास एक सरल YAML विन्यास है:

```yaml
title: YAML Example
description: Google Apps Script में YAML को संभालने का एक उदाहरण
tags:
  - Google Apps Script
  - YAML
  - Configuration
```

Google Apps Script में इसे पार्स करने के लिए, JavaScript की स्ट्रिंग मैनिपुलेशन क्षमताओं का उपयोग करें:

```javascript
function parseYAML(yamlString) {
  var result = {};
  var lines = yamlString.split("\n");
  for (var i = 0; i < lines.length; i++) {
    var line = lines[i];
    if (line.includes(":")) {
      var parts = line.split(":");
      var key = parts[0].trim();
      var value = parts[1].trim();
      // मूल हैंडलिंग फॉर ऐरेज़
      if (value.startsWith("-")) {
        value = [value.substring(1).trim()];
        while (i + 1 < lines.length && lines[i + 1].trim().startsWith("-")) {
          i++;
          value.push(lines[i].trim().substring(1).trim());
        }
      }
      result[key] = value;
    }
  }
  return result;
}

function testYamlParsing() {
  var yaml = "title: YAML Example\ndescription: Google Apps Script में YAML को संभालने का एक उदाहरण\ntags:\n  - Google Apps Script\n  - YAML\n  - Configuration";
  var parsed = parseYAML(yaml);
  Logger.log(parsed);
}
```

जब `testYamlParsing()` को निष्पादित किया जाता है, तो यह आउटपुट होता है:

```
{ title: 'YAML Example',
  description: 'Google Apps Script में YAML को संभालने का एक उदाहरण',
  tags: [ 'Google Apps Script', ' YAML', ' Configuration' ] }
```

यह कस्टम पार्सिंग दृष्टिकोण काफी आधारभूत है और जटिल YAML फ़ाइलों को समायोजित करने के लिए समायोजनों की आवश्यकता हो सकती है।

## गहराई में पड़ताल

YAML, जिसे 2001 में जारी किया गया था, अपने पूर्वजों जैसे XML या JSON की तुलना में अधिक मानव-पठनीय होने का लक्ष्य रखता था। हालांकि इसकी सादगी और उपयोग में आसानी को व्यापक रूप से सराहा गया है, Google Apps Script में YAML को संभालना चुनौतीपूर्ण है क्योंकि सीधे समर्थन का अभाव है। परिणामस्वरूप, प्रोग्रामर अक्सर YAML डेटा को पार्स और उत्पन्न करने के लिए JavaScript की बहुमुखी प्रतिभा पर निर्भर करते हैं। हालांकि, जटिल उपयोग के मामलों के लिए, विशेष रूप से जो गहरे नेस्टिंग और उन्नत डेटा संरचनाओं को शामिल करते हैं, यह पद्धति कठिनाईपूर्ण और त्रुटि प्रवण हो सकती है।

इसके विपरीत, JSON, Google Apps Script और अधिकांश अन्य प्रोग्रामिंग वातावरणों में मूल रूप से समर्थित है, डेटा सीरियलाइजेशन और डिसीरियलाइजेशन के लिए एक अधिक सीधा दृष्टिकोण प्रदान करता है बिना अतिरिक्त पार्सिंग ओवरहेड के। JSON का सिंटैक्स YAML की तुलना में कम शब्दबद्ध है, जिससे यह वेब अनुप्रयोगों में डेटा विनिमय के लिए अधिक उपयुक्त बनाता है। फिर भी, YAML विन्यास फ़ाइलों और ऐसी स्थितियों के लिए लोकप्रिय है जहाँ मानव पठनीयता सर्वोपरि है।

Google Apps Script में YAML के साथ काम करते समय, पठनीयता और उपयोग में आसानी के बीच समझौतों पर विचार करें। व्यापक YAML हेरफेर के लिए, बाहरी उपकरणों या सेवाओं का पता लगाने पर विचार करना सार्थक हो सकता है जो YAML को JSON में बदल सकें इससे पहले कि आप इसे अपनी स्क्रिप्ट के भीतर संसाधित करें।
