---
date: 2024-01-20 18:00:23.697041-07:00
description: "HTTP-\u0437\u0430\u043F\u0438\u0442 \u0434\u043E\u0437\u0432\u043E\u043B\
  \u044F\u0454 \u0432\u0430\u0448\u043E\u043C\u0443 PHP-\u0441\u043A\u0440\u0438\u043F\
  \u0442\u0443 \u0441\u043F\u0456\u043B\u043A\u0443\u0432\u0430\u0442\u0438\u0441\u044F\
  \ \u0437 \u0456\u043D\u0448\u0438\u043C\u0438 \u0441\u0435\u0440\u0432\u0435\u0440\
  \u0430\u043C\u0438. \u041C\u0438 \u0440\u043E\u0431\u0438\u043C\u043E \u0446\u0435\
  \ \u0434\u043B\u044F \u043E\u0442\u0440\u0438\u043C\u0430\u043D\u043D\u044F \u0442\
  \u0430 \u0432\u0456\u0434\u043F\u0440\u0430\u0432\u043A\u0438 \u0434\u0430\u043D\
  \u0438\u0445, \u0456\u043D\u0442\u0435\u0433\u0440\u0430\u0446\u0456\u0457 \u0437\
  \ API, \u0432\u0437\u0430\u0454\u043C\u043E\u0434\u0456\u0457 \u0456\u0437 \u0432\
  \u0435\u0431-\u2026"
lastmod: '2024-03-13T22:44:49.425207-06:00'
model: gpt-4-1106-preview
summary: "HTTP-\u0437\u0430\u043F\u0438\u0442 \u0434\u043E\u0437\u0432\u043E\u043B\
  \u044F\u0454 \u0432\u0430\u0448\u043E\u043C\u0443 PHP-\u0441\u043A\u0440\u0438\u043F\
  \u0442\u0443 \u0441\u043F\u0456\u043B\u043A\u0443\u0432\u0430\u0442\u0438\u0441\u044F\
  \ \u0437 \u0456\u043D\u0448\u0438\u043C\u0438 \u0441\u0435\u0440\u0432\u0435\u0440\
  \u0430\u043C\u0438."
title: "\u041D\u0430\u0434\u0441\u0438\u043B\u0430\u043D\u043D\u044F HTTP-\u0437\u0430\
  \u043F\u0438\u0442\u0443"
weight: 44
---

## Як це робити:
В PHP для відправлення HTTP-запитів можна використовувати cURL або file_get_contents(). Ось приклади обох:

```PHP
// Використання cURL
$ch = curl_init('http://example.com/api');
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$response = curl_exec($ch);
curl_close($ch);
echo $response;

// Використання file_get_contents()
$response = file_get_contents('http://example.com/api');
echo $response;
```
Обидва відображають відповідь від http://example.com/api.

## Поглиблений огляд
cURL у PHP — потужна бібліотека для відправлення HTTP-запитів, підтримує багато опцій. file_get_contents() простіший, але менш гнучкий.

cURL з’явився у 1997 році, і з тих пір став стандартом для веб-запитів в PHP. file_get_contents() добре підходить для простих GET-запитів. Є й інші бібліотеки, наприклад, Guzzle, які надають більше можливостей та кращу обробку помилок.

## Див. також:
- [PHP cURL](http://php.net/manual/en/book.curl.php) - офіційна документація по cURL в PHP.
- [PHP Streams](http://php.net/manual/en/book.stream.php) - офіційна документація по потоках в PHP.
- [Guzzle](http://docs.guzzlephp.org/) - сучасний HTTP-клієнт для PHP.
