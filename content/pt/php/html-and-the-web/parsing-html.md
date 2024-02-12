---
title:                "Analisando HTML"
aliases:
- /pt/php/parsing-html/
date:                  2024-02-03T19:12:33.579895-07:00
model:                 gpt-4-0125-preview
simple_title:         "Analisando HTML"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/php/parsing-html.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## O Que & Porquê?
Analisar HTML com PHP envolve extrair informações específicas de documentos HTML. Programadores realizam essa tarefa para automatizar a extração de dados, o web scraping, ou para integrar conteúdo de várias páginas da web dentro de suas aplicações, melhorando a funcionalidade sem intervenção manual.

## Como fazer:
Para analisar HTML, programadores PHP podem utilizar funções integradas ou recorrer a bibliotecas robustas como o Simple HTML DOM Parser. Aqui, exploraremos exemplos usando tanto o `DOMDocument` do PHP quanto o Simple HTML DOM Parser.

### Usando `DOMDocument`:
A classe `DOMDocument` do PHP é parte de sua extensão DOM, permitindo a análise e manipulação de documentos HTML e XML. Aqui está um exemplo rápido de como usar o `DOMDocument` para encontrar todas as imagens em um documento HTML:

```php
$html = <<<HTML
<!DOCTYPE html>
<html>
<head>
    <title>Página de Exemplo</title>
</head>
<body>
    <img src="image1.jpg" alt="Imagem 1">
    <img src="image2.jpg" alt="Imagem 2">
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

Saída de exemplo:
```
image1.jpg
image2.jpg
```

### Usando o Simple HTML DOM Parser:
Para tarefas mais complexas ou uma sintaxe mais fácil, você pode preferir usar uma biblioteca de terceiros. O Simple HTML DOM Parser é uma escolha popular, fornecendo uma interface semelhante ao jQuery para navegar e manipular estruturas HTML. Veja como usá-lo:

Primeiro, instale a biblioteca usando o Composer:
```
composer require simple-html-dom/simple-html-dom
```

Então, manipule o HTML para, por exemplo, encontrar todos os links:

```php
require_once 'vendor/autoload.php';

use simplehtmldom\HtmlWeb;

$client = new HtmlWeb();
$html = $client->load('http://www.example.com');

foreach($html->find('a') as $element) {
    echo $element->href . "\n";
}
```

Esse trecho de código buscará o conteúdo HTML de 'http://www.example.com', o analisará e imprimirá todos os hiperlinks. Lembre-se de substituir `'http://www.example.com'` pela URL real que deseja analisar.

Utilizando esses métodos, desenvolvedores PHP podem efetivamente analisar conteúdo HTML, personalizar a extração de dados conforme suas necessidades, ou integrar sem problemas o conteúdo web externo em seus projetos.
