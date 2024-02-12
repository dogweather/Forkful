---
title:                "HTMLの解析"
aliases:
- /ja/php/parsing-html/
date:                  2024-02-03T19:13:05.177864-07:00
model:                 gpt-4-0125-preview
simple_title:         "HTMLの解析"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ja/php/parsing-html.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 何となぜ？
PHPにおけるHTMLのパースとは、HTMLドキュメントから特定の情報を抽出することを指します。プログラマーがこの作業を行うのは、データ抽出の自動化、ウェブスクレイピング、または様々なウェブページのコンテンツを彼らのアプリケーション内で統合するためであり、手動での介入なしに機能性を向上させることが目的です。

## どのように：
PHPプログラマーは、ビルトイン関数を利用するか、Simple HTML DOM Parserのような堅牢なライブラリに頼ることができます。ここでは、PHPの`DOMDocument`とSimple HTML DOM Parserを使用した例を探ります。

### `DOMDocument`を使用する:
PHPの`DOMDocument`クラスは、DOM拡張の一部であり、HTMLやXMLドキュメントの解析や操作を可能にします。次は、`DOMDocument`を使用してHTMLドキュメント内のすべての画像を見つける方法の簡単な例です：

```php
$html = <<<HTML
<!DOCTYPE html>
<html>
<head>
    <title>サンプルページ</title>
</head>
<body>
    <img src="image1.jpg" alt="イメージ 1">
    <img src="image2.jpg" alt="イメージ 2">
</body>
</html>
HTML;

$doc = new DOMDocument();
@$doc->loadHTML($html);
$images = $doc->getElementsByTagName('img');

foreach ($images as $img) {
    echo $img->getAttribute('src') . "\n";
}
```

サンプル出力：
```
image1.jpg
image2.jpg
```

### Simple HTML DOM Parserを使用する:
より複雑なタスクや簡単な構文が好みの場合、サードパーティのライブラリを使用することを好むかもしれません。Simple HTML DOM Parserは人気の選択肢であり、HTML構造をナビゲートおよび操作するためのjQueryのようなインターフェースを提供します。これを使う方法は以下の通りです：

まず、Composerを使用してライブラリをインストールします：
```
composer require simple-html-dom/simple-html-dom
```

次に、例えばすべてのリンクを見つけるためにHTMLを操作します：

```php
require_once 'vendor/autoload.php';

use simplehtmldom\HtmlWeb;

$client = new HtmlWeb();
$html = $client->load('http://www.example.com');

foreach($html->find('a') as $element) {
    echo $element->href . "\n";
}
```

このコードスニペットは、'http://www.example.com'のHTMLコンテンツを取得し、解析し、すべてのハイパーリンクを出力します。パースしたい実際のURLに`'http://www.example.com'`を置き換えてください。

これらの方法を利用して、PHP開発者は効果的にHTMLコンテンツを解析し、データ抽出を自分たちのニーズに合わせて調整したり、外部のウェブコンテンツをプロジェクトにシームレスに統合することができます。
