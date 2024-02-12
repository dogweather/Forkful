---
title:                "YAML के साथ काम करना"
date:                  2024-02-03T19:26:12.933555-07:00
model:                 gpt-4-0125-preview
simple_title:         "YAML के साथ काम करना"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/c-sharp/working-with-yaml.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?
YAML, जिसका अर्थ है YAML Ain't Markup Language, एक मानव-पठनीय डेटा सीरियलाइज़ेशन प्रारूप है। प्रोग्रामर्स अक्सर इसका उपयोग कॉन्फ़िगरेशन फाइलों, प्रक्रियाओं के बीच संदेश भेजने, और डेटा स्टोरेज के लिए करते हैं क्योंकि यह XML या JSON जैसे अन्य डेटा प्रारूपों की तुलना में इसकी सादगी और पठन-शीलता के कारण है।

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
