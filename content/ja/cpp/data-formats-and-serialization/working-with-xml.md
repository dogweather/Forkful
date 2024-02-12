---
title:                "XMLの扱い方"
aliases:
- /ja/cpp/working-with-xml/
date:                  2024-01-26T04:28:36.845135-07:00
model:                 gpt-4-0125-preview
simple_title:         "XMLの扱い方"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ja/cpp/working-with-xml.md"
---

{{< edit_this_page >}}

## 何となぜ？
XMLを扱うとは、XML（eXtensible Markup Language、拡張可能マークアップ言語）データの解析、作成、および操作を意味します。プログラマーは、そのプラットフォーム中立な性質から、構造化データの交換や設定などを扱うためにXMLを管理します。

## 方法：
ここに、TinyXML-2ライブラリを使用してXMLを解析する簡単な方法があります：

```C++
#include <tinyxml2.h>
#include <iostream>

int main() {
    tinyxml2::XMLDocument doc;
    doc.Parse("<root><message>Hello, World!</message></root>");
    const char* content = doc.FirstChildElement("root")->FirstChildElement("message")->GetText();
    std::cout << content << std::endl;
    return 0;
}
```

サンプル出力：

```
Hello, World!
```

そして、これがXMLファイルを作成する方法です：

```C++
#include <tinyxml2.h>
#include <iostream>

int main() {
    tinyxml2::XMLDocument doc;
    auto* declaration = doc.NewDeclaration();
    doc.InsertFirstChild(declaration);
    auto* root = doc.NewElement("root");
    doc.InsertEndChild(root);
    auto* message = doc.NewElement("message");
    message->SetText("Hello, World!");
    root->InsertEndChild(message);
    doc.SaveFile("output.xml");
    return 0;
}
```

これにより、次の内容を持つXMLファイル`output.xml`が生成されます：

```xml
<?xml version="1.0"?>
<root>
    <message>Hello, World!</message>
</root>
```

## 深掘り
XMLは90年代後半から、Webサービスやデータストレージにおいて重要な役割を果たしてきました。現在、JSONやYAMLが設定や相互運用性において一般的になっていますが、XMLは多くのエンタープライズシステムで依然として重要です。C++でのXML解析は、手動でのDOM/SAX解析という古典的な方法に感じられることがあります。幸い、TinyXML-2のようなライブラリがこれを簡素化しています。C++にはビルトインのXMLサポートがなく、TinyXML-2、pugixml、Xercesのようなライブラリが難しい部分を包摂しています。

## 参照
- TinyXML-2ドキュメント：https://leethomason.github.io/tinyxml2/
- pugixmlライブラリ：https://pugixml.org/
- Xerces-C++パーサ：https://xerces.apache.org/xerces-c/
- W3C XML仕様：https://www.w3.org/XML/
