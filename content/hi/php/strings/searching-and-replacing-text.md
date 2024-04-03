---
date: 2024-01-20 17:58:20.903771-07:00
description: "Searching and replacing text in PHP \u092E\u0924\u0932\u092C \u0939\u0948\
  \ \u0926\u093F\u090F \u0917\u090F \u091F\u0947\u0915\u094D\u0938\u094D\u091F \u0915\
  \u094B \u0922\u0942\u0901\u0922\u0928\u093E \u0914\u0930 \u092C\u0926\u0932\u0928\
  \u093E\u0964 Programmers \u0907\u0938\u0947 \u0915\u0930\u0924\u0947 \u0939\u0948\
  \u0902 \u0921\u0947\u091F\u093E \u0915\u094B \u092B\u0949\u0930\u094D\u092E\u0947\
  \u091F \u092F\u093E \u0905\u092A\u0921\u0947\u091F \u0915\u0930\u0928\u0947 \u0915\
  \u0947 \u0932\u093F\u090F, \u091C\u0948\u0938\u0947 \u0915\u093F\u0938\u0940\u2026"
lastmod: '2024-03-13T22:44:52.451678-06:00'
model: gpt-4-1106-preview
summary: "Searching and replacing text in PHP \u092E\u0924\u0932\u092C \u0939\u0948\
  \ \u0926\u093F\u090F \u0917\u090F \u091F\u0947\u0915\u094D\u0938\u094D\u091F \u0915\
  \u094B \u0922\u0942\u0901\u0922\u0928\u093E \u0914\u0930 \u092C\u0926\u0932\u0928\
  \u093E\u0964 Programmers \u0907\u0938\u0947 \u0915\u0930\u0924\u0947 \u0939\u0948\
  \u0902 \u0921\u0947\u091F\u093E \u0915\u094B \u092B\u0949\u0930\u094D\u092E\u0947\
  \u091F \u092F\u093E \u0905\u092A\u0921\u0947\u091F \u0915\u0930\u0928\u0947 \u0915\
  \u0947 \u0932\u093F\u090F, \u091C\u0948\u0938\u0947 \u0915\u093F\u0938\u0940 document\
  \ \u092E\u0947\u0902 \u0915\u094B\u0908 \u0936\u092C\u094D\u0926 \u092C\u0926\u0932\
  \u0928\u093E\u0964."
title: "\u092A\u093E\u0920 \u0916\u094B\u091C\u0928\u093E \u0914\u0930 \u092C\u0926\
  \u0932\u0928\u093E"
weight: 10
---

## How to: (कैसे करें:)
PHP में text search और replace के लिए `str_replace` function का इस्तेमाल करते हैं:

```PHP
<?php
$originalText = 'Hello World';
$search = 'World';
$replaceWith = 'PHP';
$newText = str_replace($search, $replaceWith, $originalText);

echo $newText;  // Output: Hello PHP
?>
```

Regular expressions के लिए `preg_replace` function का इस्तेमाल करते हैं:

```PHP
<?php
$originalText = 'The quick brown fox jumps over the lazy dog';
$pattern = '/brown fox/';
$replacement = 'black cat';
$newText = preg_replace($pattern, $replacement, $originalText);

echo $newText;  // Output: The quick black cat jumps over the lazy dog
?>
```

## Deep Dive (गहराई में जानकारी):
Search और replace functionality PHP में बहुत पहले से है। `str_replace` simple strings के लिए है, जबकि `preg_replace` complex patterns (regular expressions) के लिए है। Alternatives में string functions जैसे के `strpos`, और `substr_replace` शामिल हैं। Performance-wise, `str_replace` `preg_replace` से तेज़ होता है जब patterns simple हों, क्योंकि regular expressions CPU को ज्यादा use करते हैं।

## See Also (देखें भी):
- PHP official documentation on `str_replace`: [php.net/manual/en/function.str-replace.php](https://www.php.net/manual/en/function.str-replace.php)
- PHP official documentation on `preg_replace`: [php.net/manual/en/function.preg-replace.php](https://www.php.net/manual/en/function.preg-replace.php)
- Regular Expressions Basic Syntax: [regular-expressions.info](https://www.regular-expressions.info/)
- `strpos` for finding the position of a substring in a string: [php.net/manual/en/function.strpos.php](https://www.php.net/manual/en/function.strpos.php)
- `substr_replace` for replacing text within a string: [php.net/manual/en/function.substr-replace.php](https://www.php.net/manual/en/function.substr-replace.php)
