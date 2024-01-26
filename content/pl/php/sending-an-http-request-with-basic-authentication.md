---
title:                "Wysyłanie zapytania http z podstawową autoryzacją"
date:                  2024-01-20T18:02:09.811628-07:00
model:                 gpt-4-1106-preview
simple_title:         "Wysyłanie zapytania http z podstawową autoryzacją"
programming_language: "PHP"
category:             "PHP"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/php/sending-an-http-request-with-basic-authentication.md"
---

{{< edit_this_page >}}

## What & Why? (Co i Dlaczego?)
Wysyłanie żądania HTTP z podstawową autentykacją to proces, gdzie serwer oczekuje loginu i hasła do wykonania akcji. Programiści robią to dla zabezpieczenia dostępu do zasobów.

## How to: (Jak to zrobić:)
W PHP możesz użyć cURL lub context stream. Przykład z cURL:

```PHP
<?php
$url = 'http://example.com/api/data';
$username = 'user';
$password = 'pass';

$ch = curl_init($url);
curl_setopt($ch, CURLOPT_HTTPAUTH, CURLAUTH_BASIC);
curl_setopt($ch, CURLOPT_USERPWD, "$username:$password");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);
curl_close($ch);

if($httpCode == 200) {
    echo "Odpowiedź serwera: " . $response;
} else {
    echo "Błąd: " . $httpCode;
}
?>
```

Możesz też użyć stream context:

```PHP
<?php
$url = 'http://example.com/api/data';
$username = 'user';
$password = 'pass';
$options = [
    'http' => [
        'header' => 'Authorization: Basic ' . base64_encode("$username:$password"),
        'method' => 'GET'
    ]
];

$context  = stream_context_create($options);
$result = file_get_contents($url, false, $context);

if($result !== FALSE) {
    echo "Odpowiedź serwera: " . $result;
} else {
    echo "Błąd podczas wykonywania żądania.";
}
?>
```

## Deep Dive (Wnikliwa analiza)
HTTP Basic Authentication to stary, ale prosty sposób na uwierzytelnienie. Jest łatwy w implementacji, ale wysyła dane w niezaszyfrowanej formie, więc używaj go tylko przez HTTPS!

Alternatywy? OAuth, tokeny API, sesje. Ale Basic Auth jest nadal używany, bo jest proste i wspierane "out-of-the-box".

Kiedy używasz cURL, pamiętaj o obsłudze błędów i właściwej konfiguracji. Z `stream_context`, trzeba się zabezpieczyć przed błędami z `file_get_contents`.

## See Also (Zobacz również)
- PHP cURL: https://www.php.net/manual/en/book.curl.php
- HTTP authentication with PHP: https://www.php.net/manual/en/features.http-auth.php
- Secure HTTP: https://en.wikipedia.org/wiki/HTTPS
- HTTP Basic Authentication standard: https://tools.ietf.org/html/rfc7617
