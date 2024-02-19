---
aliases:
- /pl/typescript/sending-an-http-request/
date: 2024-01-20 18:00:46.493299-07:00
description: "Wysy\u0142anie zapytania HTTP pozwala naszej aplikacji porozumiewa\u0107\
  \ si\u0119 z serwerem, wymieniaj\u0105c dane. Programi\u015Bci robi\u0105 to, by\
  \ pobra\u0107, stworzy\u0107, aktualizowa\u0107\u2026"
lastmod: 2024-02-18 23:08:49.345004
model: gpt-4-1106-preview
summary: "Wysy\u0142anie zapytania HTTP pozwala naszej aplikacji porozumiewa\u0107\
  \ si\u0119 z serwerem, wymieniaj\u0105c dane. Programi\u015Bci robi\u0105 to, by\
  \ pobra\u0107, stworzy\u0107, aktualizowa\u0107\u2026"
title: "Wysy\u0142anie \u017C\u0105dania HTTP"
---

{{< edit_this_page >}}

## What & Why? (Co i Dlaczego?)
Wysyłanie zapytania HTTP pozwala naszej aplikacji porozumiewać się z serwerem, wymieniając dane. Programiści robią to, by pobrać, stworzyć, aktualizować lub usunąć zasoby - kluczowe operacje w aplikacjach internetowych.

## How to: (Jak to zrobić:)
```TypeScript
import axios from 'axios';

// GET request do pobrania danych użytkownika
axios.get('https://jsonplaceholder.typicode.com/users/1')
  .then(response => {
    console.log(response.data);
  })
  .catch(error => console.error('There was an error!', error));

// POST request do stworzenia nowego użytkownika
axios.post('https://jsonplaceholder.typicode.com/users', {
  name: 'Jan Kowalski',
  username: 'jankowalski',
})
.then(response => {
  console.log('User created:', response.data);
})
.catch(error => console.error('Error creating user', error));
```

Sample output:
```
User created: {name: 'Jan Kowalski', username: 'jankowalski', id: 11}
```

## Deep Dive (Głębsze zanurzenie)
Wysyłanie żądań HTTP ma długą historię, ukorzenioną w początkach internetu, kiedy to Tim Berners-Lee wynalazł HTTP. Alternatywnie do axios, używać można Fetch API – natywna funkcja JavaScriptu. Axios oferuje jednak więcej funkcji, np. automatyczną transformację JSON. Wysyłając żądanie, należy zrozumieć metody takie jak GET, POST, a także statusy odpowiedzi HTTP (np. 200 oznacza sukces, a 404 - nie znaleziono zasobu).

## See Also (Zobacz także)
- [MDN Web Docs on HTTP](https://developer.mozilla.org/pl/docs/Web/HTTP)
- [Axios documentation](https://axios-http.com/docs/intro)
- [Fetch API on MDN Web Docs](https://developer.mozilla.org/pl/docs/Web/API/Fetch_API)
- [Understanding REST APIs](https://restfulapi.net/)
