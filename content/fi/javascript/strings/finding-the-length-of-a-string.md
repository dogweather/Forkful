---
title:                "Merkkijonon pituuden selvittäminen"
date:                  2024-01-20T17:47:44.087795-07:00
model:                 gpt-4-1106-preview
simple_title:         "Merkkijonon pituuden selvittäminen"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/javascript/finding-the-length-of-a-string.md"
---

{{< edit_this_page >}}

## What & Why? - Mitä ja Miksi?
Selvitetään merkkijonon pituutta (`length`-ominaisuus) tietääksemme, montako merkkiä jono sisältää. Sitä tarvitaan esimerkiksi silloin, kun validoidaan käyttäjän syötteitä tai manipuloidaan tekstidataa.

## How to: - Kuinka tehdään:
```javascript
let greeting = "Hei maailma!";
console.log(greeting.length); // Tulostaa 12

let emptyString = "";
console.log(emptyString.length); // Tulostaa 0

let emojiString = "😊";
console.log(emojiString.length); // Tulostaa 2, koska Unicode-emotikonit voivat olla monimerkkisiä
```

## Deep Dive - Syväsukellus:
Merkkijonon pituuden selvittäminen JavaScriptillä on helppoa ja suoraviivaista: käytä `length`-ominaisuutta. Historiallisesti tämä ominaisuus on ollut osa JavaScriptiä alusta asti, eli ECMAScript 1 -versiosta lähtien.

Ennen ES6:ta, jos halusi luoda uuden merkkijonon pituuden perusteella, ainoa tapa oli käyttää silmukoita tai funktioita. ES6 toi mukanaan `String.prototype.repeat`-metodin, joka helpottaa tätä tehtävää.

Unicode-merkkijonojen kanssa pitää olla tarkkana, koska JavaScript käsittelee Unicode-merkkejä erikoisesti. Esimerkiksi jotkut emotikonit voivat koostua useammasta Unicode-skaalan merkistä, mikä tarkoittaa että `length`-ominaisuus voi antaa hämäävän arvon.

## See Also - Katso Myös:
- MDN Web Docs - String.length: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
- JavaScript Unicode pitfalls: [http://mathiasbynens.be/notes/javascript-unicode](http://mathiasbynens.be/notes/javascript-unicode)
- Understanding ES6: [https://leanpub.com/understandinges6/read](https://leanpub.com/understandinges6/read)
