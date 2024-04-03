---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:26:12.933555-07:00
description: "YAML, \u091C\u093F\u0938\u0915\u093E \u0905\u0930\u094D\u0925 \u0939\
  \u0948 YAML Ain't Markup Language, \u090F\u0915 \u092E\u093E\u0928\u0935-\u092A\u0920\
  \u0928\u0940\u092F \u0921\u0947\u091F\u093E \u0938\u0940\u0930\u093F\u092F\u0932\
  \u093E\u0907\u091C\u093C\u0947\u0936\u0928 \u092A\u094D\u0930\u093E\u0930\u0942\u092A\
  \ \u0939\u0948\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\
  \u094D\u0938 \u0905\u0915\u094D\u0938\u0930 \u0907\u0938\u0915\u093E \u0909\u092A\
  \u092F\u094B\u0917 \u0915\u0949\u0928\u094D\u092B\u093C\u093F\u0917\u0930\u0947\u0936\
  \u0928 \u092B\u093E\u0907\u0932\u094B\u0902,\u2026"
lastmod: '2024-03-13T22:44:52.367201-06:00'
model: gpt-4-0125-preview
summary: "YAML, \u091C\u093F\u0938\u0915\u093E \u0905\u0930\u094D\u0925 \u0939\u0948\
  \ YAML Ain't Markup Language, \u090F\u0915 \u092E\u093E\u0928\u0935-\u092A\u0920\
  \u0928\u0940\u092F \u0921\u0947\u091F\u093E \u0938\u0940\u0930\u093F\u092F\u0932\
  \u093E\u0907\u091C\u093C\u0947\u0936\u0928 \u092A\u094D\u0930\u093E\u0930\u0942\u092A\
  \ \u0939\u0948\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\
  \u094D\u0938 \u0905\u0915\u094D\u0938\u0930 \u0907\u0938\u0915\u093E \u0909\u092A\
  \u092F\u094B\u0917 \u0915\u0949\u0928\u094D\u092B\u093C\u093F\u0917\u0930\u0947\u0936\
  \u0928 \u092B\u093E\u0907\u0932\u094B\u0902, \u092A\u094D\u0930\u0915\u094D\u0930\
  \u093F\u092F\u093E\u0913\u0902 \u0915\u0947 \u092C\u0940\u091A \u0938\u0902\u0926\
  \u0947\u0936 \u092D\u0947\u091C\u0928\u0947, \u0914\u0930 \u0921\u0947\u091F\u093E\
  \ \u0938\u094D\u091F\u094B\u0930\u0947\u091C \u0915\u0947 \u0932\u093F\u090F \u0915\
  \u0930\u0924\u0947 \u0939\u0948\u0902 \u0915\u094D\u092F\u094B\u0902\u0915\u093F\
  \ \u092F\u0939 XML \u092F\u093E JSON \u091C\u0948\u0938\u0947 \u0905\u0928\u094D\
  \u092F \u0921\u0947\u091F\u093E \u092A\u094D\u0930\u093E\u0930\u0942\u092A\u094B\
  \u0902 \u0915\u0940 \u0924\u0941\u0932\u0928\u093E \u092E\u0947\u0902 \u0907\u0938\
  \u0915\u0940 \u0938\u093E\u0926\u0917\u0940 \u0914\u0930 \u092A\u0920\u0928-\u0936\
  \u0940\u0932\u0924\u093E \u0915\u0947 \u0915\u093E\u0930\u0923 \u0939\u0948\u0964\
  ."
title: "YAML \u0915\u0947 \u0938\u093E\u0925 \u0915\u093E\u092E \u0915\u0930\u0928\
  \u093E"
weight: 41
---

## कैसे करें:
C# में YAML के लिए कोई बिल्ट-इन सपोर्ट नहीं है, लेकिन आप *YamlDotNet* जैसे तीसरे पक्ष के पुस्तकालयों का उपयोग करके YAML के साथ आसानी से काम कर सकते हैं। सबसे पहले, आपको YamlDotNet पैकेज इंस्टॉल करना होगा:

```bash
Install-Package YamlDotNet -Version 11.2.1
```

### YAML पढ़ना:
मान लीजिए आपके पास `config.yaml` नामक एक YAML फ़ाइल है जिसमें निम्नलिखित सामग्री है:
```yaml
appSettings:
  name: MyApp
  version: 1.0.0
```

आप इस YAML फाइल को C# में इस तरह पढ़ और पार्स कर सकते हैं:
```csharp
using System;
using System.IO;
using YamlDotNet.Serialization;
using YamlDotNet.Serialization.NamingConventions;

public class AppConfig
{
    public AppSettings appSettings { get; set; }
}

public class AppSettings
{
    public string name { get; set; }
    public string version { get; set; }
}

class Program
{
    static void Main(string[] args)
    {
        var yaml = File.ReadAllText("config.yaml");
        var deserializer = new DeserializerBuilder()
            .WithNamingConvention(UnderscoredNamingConvention.Instance) // समुचित नामकरण सम्मेलन के अनुसार समायोजित करें
            .Build();

        var config = deserializer.Deserialize<AppConfig>(yaml);

        Console.WriteLine($"Name: {config.appSettings.name}, Version: {config.appSettings.version}");
    }
}
```
**नमूना आउटपुट:**
```
Name: MyApp, Version: 1.0.0
```

### YAML लिखना:
YAML फ़ाइल में डेटा लिखने के लिए, YamlDotNet से `Serializer` क्लास का उपयोग करें। यहाँ एक ऑब्जेक्ट को वापस YAML में सीरियलाइज़ करने का तरीका है:

```csharp
using System;
using System.IO;
using YamlDotNet.Serialization;
using YamlDotNet.Serialization.NamingConventions;

class Program
{
    static void Main(string[] args)
    {
        var config = new AppConfig
        {
            appSettings = new AppSettings
            {
                name = "MyApp",
                version = "2.0.0"
            }
        };

        var serializer = new SerializerBuilder()
            .WithNamingConvention(UnderscoredNamingConvention.Instance) // समुचित नामकरण सम्मेलन के अनुसार समायोजित करें
            .Build();

        var yaml = serializer.Serialize(config);
        File.WriteAllText("updatedConfig.yaml", yaml);

        Console.WriteLine(yaml);
    }
}
```
**नमूना आउटपुट:**
```yaml
appSettings:
  name: MyApp
  version: 2.0.0
```

यह सीधे तरीके से दर्शाता है कि आप अपने C# परियोजनाओं में YAML के साथ कुशलतापूर्वक कैसे काम कर सकते हैं, जिससे YamlDotNet पुस्तकालय का उपयोग करके YAML फ़ाइलों से पढ़ना और लिखना सरल हो जाता है।
