---
date: 2024-01-20 18:02:37.871553-07:00
description: "Wysy\u0142anie \u017C\u0105dania HTTP z podstawow\u0105 autoryzacj\u0105\
  \ to proces dodawania nag\u0142\xF3wka autoryzacyjnego do \u017C\u0105dania HTTP,\
  \ aby potwierdzi\u0107, \u017Ce mamy dost\u0119p. Programi\u015Bci\u2026"
lastmod: '2024-03-13T22:44:35.932203-06:00'
model: gpt-4-1106-preview
summary: "Wysy\u0142anie \u017C\u0105dania HTTP z podstawow\u0105 autoryzacj\u0105\
  \ to proces dodawania nag\u0142\xF3wka autoryzacyjnego do \u017C\u0105dania HTTP,\
  \ aby potwierdzi\u0107, \u017Ce mamy dost\u0119p."
title: "Wysy\u0142anie zapytania http z podstawow\u0105 autoryzacj\u0105"
weight: 45
---

## How to: (Jak to zrobić:)
Ruby używa `net/http` do wysyłania żądań HTTP. Dołączanie podstawowej autoryzacji jest proste:

```Ruby
require 'net/http'
require 'uri'

uri = URI('http://example.com/secrets')
username = 'foo'
password = 'bar'

request = Net::HTTP::Get.new(uri)
request.basic_auth(username, password)

response = Net::HTTP.start(uri.hostname, uri.port) do |http|
  http.request(request)
end

puts response.body
```

Jeśli wszystko jest poprawne, odpowiedź będzie zawierać dane, do których dostęp uzyskaliśmy.

## Deep Dive (W Głębi Tematu)
Podstawowa autoryzacja HTTP to stara metoda (RFC 7617), niezbyt bezpieczna – używa base64, a nie szyfrowania. Alternatywy to Digest Access Authentication lub bardziej bezpieczne tokeny, jak OAuth.

Podstawowa autoryzacja w Ruby jest prosta – dodaje zakodowany login i hasło do nagłówka żądania. W realnych aplikacjach zaleca się użycie HTTPS, by zabezpieczyć dane uwierzytelniające.

## See Also (Zobacz również)
- Dokumentacja Basic Authentication w RFC 7617: [The 'Basic' HTTP Authentication Scheme](https://tools.ietf.org/html/rfc7617)
- Wprowadzenie do autoryzacji HTTP: [HTTP Authentication: Basic and Digest Access Authentication](https://tools.ietf.org/html/rfc2617)
