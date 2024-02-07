---
title:                "Merkkijonon interpolointi"
date:                  2024-01-20T17:50:51.017516-07:00
model:                 gpt-4-1106-preview
simple_title:         "Merkkijonon interpolointi"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/elixir/interpolating-a-string.md"
---

{{< edit_this_page >}}

## What & Why?
Mikä on merkkijonointerpolointi, ja miksi sitä käytetään? Elixirissä merkkijonointerpolointi tarkoittaa muuttujan arvon "liittämistä" merkkijonoon. Sitä käytetään dynaamisen tekstin luontiin, mikä tekee koodista selkeämpää ja ylläpidettävämpää.

## How to:
Interpolointi Elixirissä hoituu `#{}` syntaksilla. Tässä pari esimerkkiä:

```elixir
nimi = "Pekka"
tervehdys = "Hei, #{nimi}!"
IO.puts(tervehdys)
```

Tulostuu:
```
Hei, Pekka!
```

Toinen esimerkki laskutoimituksen kanssa:

```elixir
luku = 4
viesti = "Kertolaskun tulos on #{luku * 2}."
IO.puts(viesti)
```

Tulostuu:
```
Kertolaskun tulos on 8.
```

## Deep Dive
Merkkijonot ja interpolointi ovat keskeinen osa ohjelmointia. Ruby-yhteisöstä vaikutteensa saaneessa Elixirissä syntaksi on suunniteltu olemaan intuitiivinen. Historiallisesti tämä on peruja sellaisista kielistä kuin Perl ja sen myötä Ruby, jotka molemmat painottivat helppolukuisuutta ja tehokkuutta string-käsittelyssä.

Vaihtoehtoisesti voitaisiin käyttää merkkijonoyhdistämistä, mutta se saattaa johtaa sekavaan ja vaikeasti ymmärrettävään koodiin, jos yhdistettäviä osia on paljon.

Toteutuksen yksityiskohdista puhuttaessa, Elixirin string-interpolointi on makro, joka korvataan käännösaikana. Tämä tarkoittaa sitä, että suorituskykyyn ei tule hidastusta ajonaikaisen evaluoinnin seurauksena.

## See Also
- Elixirin virallinen dokumentaatio merkkijonoista: [https://hexdocs.pm/elixir/String.html](https://hexdocs.pm/elixir/String.html)
- Programming Elixir -kirja, jossa käsitellään string-interpolointia: [https://pragprog.com/book/elixir16/programming-elixir-1-6](https://pragprog.com/book/elixir16/programming-elixir-1-6)
- Tutki Elixirin makroja tarkemmin: [https://elixir-lang.org/getting-started/meta/macros.html](https://elixir-lang.org/getting-started/meta/macros.html)
