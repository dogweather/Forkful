---
aliases:
- /he/php/downloading-a-web-page/
date: 2024-01-20 17:44:26.280428-07:00
description: Downloading a web page means grabbing the HTML content from a URL. Programmers
  do this to process, analyze or display the content in a different context.
lastmod: 2024-02-18 23:08:52.930577
model: gpt-4-1106-preview
summary: Downloading a web page means grabbing the HTML content from a URL. Programmers
  do this to process, analyze or display the content in a different context.
title: "\u05D4\u05D5\u05E8\u05D3\u05EA \u05D3\u05E3 \u05D0\u05D9\u05E0\u05D8\u05E8\
  \u05E0\u05D8"
---

{{< edit_this_page >}}

## מה ולמה?
Downloading a web page means grabbing the HTML content from a URL. Programmers do this to process, analyze or display the content in a different context.

## איך לעשות:
```php
<?php
$url = 'http://example.com';
$content = file_get_contents($url);
if ($content !== false) {
    // Do something with the content
    echo $content;
} else {
    // Handle the error
    echo "Couldn't download the page.";
}
?>
```

Sample Output:
```html
<!doctype html>
<html>
<head>
    <title>Example Domain</title>
...
</head>
<body>
...
</body>
</html>
```

## עיון מעמיק:
Back in the day, we had to use CURL for downloading web pages, which gave us more control but was verbose. Now, `file_get_contents` is a handy alternative for simple tasks. But remember, for complex tasks or error handling, CURL is still preferable. When using `file_get_contents()`, check for its return value, false, which indicates failure. To handle HTTP headers, timeouts, and other finer details, delve into `stream_context_create()`.

## ראה גם:
- PHP Manual on `file_get_contents`: https://www.php.net/manual/en/function.file-get-contents.php
- PHP Manual on `stream_context_create()`: https://www.php.net/manual/en/function.stream-context-create.php
- PHP CURL Documentation for advanced usage: https://www.php.net/manual/en/book.curl.php
