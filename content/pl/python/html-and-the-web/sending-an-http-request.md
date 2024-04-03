---
date: 2024-01-20 18:00:17.565958-07:00
description: "Wys\u0142anie \u017C\u0105dania HTTP (Hypertext Transfer Protocol) to\
  \ spos\xF3b, w jaki nasz program mo\u017Ce komunikowa\u0107 si\u0119 z serwerami\
  \ w Internecie. Robimy to, \u017Ceby pobra\u0107\u2026"
lastmod: '2024-03-13T22:44:34.946102-06:00'
model: gpt-4-1106-preview
summary: "Wys\u0142anie \u017C\u0105dania HTTP (Hypertext Transfer Protocol) to spos\xF3\
  b, w jaki nasz program mo\u017Ce komunikowa\u0107 si\u0119 z serwerami w Internecie."
title: "Wysy\u0142anie \u017C\u0105dania HTTP"
weight: 44
---

## Jak to zrobić:
Użyjemy `requests`, łatwej w użyciu biblioteki pozwalającej na wysyłanie żądań HTTP. Instalacja to linijka w terminalu:

```Python
pip install requests
```

A oto prosty przykład użycia:

```Python
import requests

response = requests.get('https://api.github.com')
print(response.status_code)
print(response.content)
```

Output może być taki:

```Python
200
b'{"current_user_url":"https://api.github.com/user","current_user_authorizations_html_url":"https://github.com/settings/connections/applications{/client_id}",...}'
```

Kod `200` mówi nam, że żądanie się powiodło.

## Deep Dive
Protokół HTTP istnieje od 1991 roku. Z czasem ewoluował – mamy już HTTP/2 i eksperymentujemy z HTTP/3. Alternatywą dla biblioteki `requests` może być `http.client` wbudowany w Pythona, choć nie jest tak wygodny w użyciu.

Biblioteka `requests` obsługuje sesje, co pozwala na przechowywanie ciasteczek czy utrzymywanie stałego nagłówka przez wiele żądań. Wsparcie dla HTTPS jest wbudowane, a co za tym idzie, szyfrowanie danych również. Kiedy wysyłasz żądanie, `requests` automatycznie koduje parametry, a odpowiedzi mogą być łatwo przekształcone w struktury danych JSON.

## Zobacz również
- [Dokumentacja `requests`](https://requests.readthedocs.io/en/master/)
- [Przewodnik po żądaniach HTTP w Pythonie](https://realpython.com/python-requests/)
- [HTTP/3 Explained](https://http3-explained.haxx.se/en/)
- [Dokumentacja `http.client`](https://docs.python.org/3/library/http.client.html)

Pamiętaj, że praktyka czyni mistrza – eksperymentuj z wysyłaniem różnych typów żądań i badaniem odpowiedzi. W sieci można znaleźć mnóstwo API do wypróbowania. Powodzenia!
