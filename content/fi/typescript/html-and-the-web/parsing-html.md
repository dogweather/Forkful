---
aliases:
- /fi/typescript/parsing-html/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:13:15.123430-07:00
description: "HTML:n j\xE4sent\xE4minen tarkoittaa HTML-koodin l\xE4pik\xE4ymist\xE4\
  \ l\xF6yt\xE4\xE4kseen, poimiakseen tai manipuloidakseen tietoa. Ohjelmoijat tekev\xE4\
  t sit\xE4 vuorovaikuttaakseen\u2026"
lastmod: 2024-02-18 23:09:07.316346
model: gpt-4-0125-preview
summary: "HTML:n j\xE4sent\xE4minen tarkoittaa HTML-koodin l\xE4pik\xE4ymist\xE4 l\xF6\
  yt\xE4\xE4kseen, poimiakseen tai manipuloidakseen tietoa. Ohjelmoijat tekev\xE4\
  t sit\xE4 vuorovaikuttaakseen\u2026"
title: "HTML:n j\xE4sennys"
---

{{< edit_this_page >}}

## Mikä & Miksi?

HTML:n jäsentäminen tarkoittaa HTML-koodin läpikäymistä löytääkseen, poimiakseen tai manipuloidakseen tietoa. Ohjelmoijat tekevät sitä vuorovaikuttaakseen verkkosisällön kanssa—ehkä kaapiakseen dataa tai automatisoidakseen selaimia.

## Kuinka:

Aloittaaksesi, asenna kirjasto kuten `node-html-parser`. Tässä on terminaalikomento:

```bash
npm install node-html-parser
```

Nyt jäsentäkäämme jotakin perus HTML:ää TypeScriptissä:

```typescript
import { parse } from 'node-html-parser';

const html = `<ul class="fruits">
                <li>Omena</li>
                <li>Banaani</li>
              </ul>`;

const root = parse(html);
console.log(root.querySelector('.fruits').textContent);  // "Omena Banaani"
```

Ja jos haluat napata vain banaanit:

```typescript
const bananas = root.querySelectorAll('li')[1].textContent;
console.log(bananas);  // "Banaani"
```

## Syväsukellus

HTML:n jäsentäminen ei ole uutta—se on ollut olemassa verkon alkupäivistä lähtien. Aluksi kehittäjät ovat ehkä käyttäneet säännöllisiä lausekkeita, mutta se muuttui nopeasti sekavaksi. Sitten tuli DOM Parser: vakaa, mutta selainrajattu.

Kirjastot kuten `node-html-parser` poistavat tuskan. Ne antavat sinun kyselyä HTML:ää kuten tekisit jQueryllä, mutta palvelinpuolella Node.js:n kanssa. Se on nopea, sietää likaista HTML:ää, ja on DOM-ystävällinen.

On myös `jsdom`, joka simuloii koko selainympäristöä. Se on raskaampi mutta perusteellisempi, luoden täysin puhalletun Document Object Model (DOM) manipulointia ja vuorovaikutusta varten.

Älkäämme unohtako Cheeriotakaan. Se yhdistää nopeuden jQueryn kaltaiseen syntaksiin ja pienempään jalanjälkeen, sijoittuen iloisesti näiden kahden väliin.

## Katso Myös

Jos janotat lisää, kasta varpaasi näihin:
- [DOM-jäsentämisen ja serialisoinnin W3C-spesifikaatio](https://www.w3.org/TR/DOM-Parsing/)
- [node-html-parser GitHubissa](https://github.com/taoqf/node-html-parser)
- [jsdom GitHub-repositorio](https://github.com/jsdom/jsdom)
- [Cheerion verkkosivusto](https://cheerio.js.org/)
