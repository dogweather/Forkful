---
date: 2024-01-20 18:00:11.937066-07:00
description: "HTTP-pyynt\xF6 on web-palvelimen kanssa kommunikoinnin tavallinen tapa.\
  \ Koodarit l\xE4hett\xE4v\xE4t HTTP-pyynt\xF6j\xE4 vaihtaakseen dataa palvelinten\
  \ ja front-end\u2026"
lastmod: '2024-03-13T22:44:56.946739-06:00'
model: gpt-4-1106-preview
summary: "HTTP-pyynt\xF6 on web-palvelimen kanssa kommunikoinnin tavallinen tapa."
title: "HTTP-pyynn\xF6n l\xE4hett\xE4minen"
weight: 44
---

## How to: (Kuinka:)
Käytetään esimerkkinä Fetch API:

```Javascript
// Lähetetään GET-pyyntö
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Haku epäonnistui:', error));

// Lähetetään POST-pyyntö
fetch('https://api.example.com/submit', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({ name: 'Esimerkki' })
})
.then(response => response.json())
.then(data => console.log('Vastaus:', data))
.catch(error => console.error('Lähetys epäonnistui:', error));
```

Tuloste GET-pyynnölle:
```Javascript
{ "name": "Esimerkki", "id": "123" }
```

Tuloste POST-pyynnölle:
```Javascript
{ "status": "success", "message": "Data lähetetty" }
```

## Deep Dive (Sukellus syvyyksiin):
Alkuun HTTP-pyynnöt tehtiin XMLHttpRequest-objektin avulla, joka oli joskus monimutkainen. Fetch API on moderni, lupauksiin (promises) perustuva vaihtoehto, joka tarjoaa selkeämmän ja joustavamman tavan tehdä verkkopyyntöjä. Vaikka Fetch on nykyään standardi, vanhoja projekteja tai selaimia varten on joskus tarve käyttää polyfillejä tai XMLHttpRequestia.

HTTP-pyynnöt voivat käyttää useita metodeja, kuten GET, POST, PUT ja DELETE, riippuen toiminnasta, jota yritetään suorittaa. Käyttöoikeuksista (CORS) huolehtiminen on myös olennaista, kun lähetetään pyyntöjä eri alkuperien välillä.

## See Also (Lisäksi):
- MDN Web Docs Fetch API: [https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
- XMLHttpRequest (vanhempi tapa): [https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)
- HTTP-pyyntömetodit: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
- CORS (Cross-Origin Resource Sharing): [https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
