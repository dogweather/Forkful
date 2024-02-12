---
title:                "Koodin järjestäminen funktioihin"
aliases:
- /fi/bash/organizing-code-into-functions/
date:                  2024-01-26T01:09:12.560901-07:00
model:                 gpt-4-1106-preview
simple_title:         "Koodin järjestäminen funktioihin"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/bash/organizing-code-into-functions.md"
---

{{< edit_this_page >}}

## Mitä ja miksi?
Koodin jakaminen funktioihin tarkoittaa skriptien pilkkomista pienempiin, uudelleenkäytettäviin lohkoihin, jotka suorittavat tiettyjä tehtäviä. Se tekee koodista selkeämmän, ymmärrettävämmän ja helpomman virheenjäljityksen kannalta.

## Miten:
Luo yksinkertainen funktio Bashissa:

```Bash
greet() {
  echo "Hello, $1!"
}
```

Käytä sitä kutsumalla funktiota parametrin kanssa:

```Bash
greet "World"  # Tulostus: Hello, World!
```

Funktiot voivat palauttaa arvoja käyttäen `return`-komentoa numeerisille tilakoodeille (ei kuitenkaan varsinaisten tietojen palautukseen):

```Bash
add() {
  return $(($1 + $2))
}

add 3 4
echo $?  # Tulostus: 7
```

Huomaa, että `$?` tallentaa viimeisen komennon paluuarvon, joka on `add`-funktion numeerinen tulos.

## Syventävä osio
Bashissa funktiot ovat olleet tapa paketoida koodia jo alkuperäisestä versiosta lähtien. Historiallisesti, funktioiden käyttö heijastelee 1960-luvulla esitettyjä rakenteellisen ohjelmoinnin periaatteita, joiden tavoitteena oli parantaa koodin laatua.

Vaihtoehtoja funktioille ovat muiden skriptitiedostojen lähdekoodin sisällyttäminen tai aliasten käyttö, mutta nämä eivät tarjoa samaa modulaarisuuden ja uudelleenkäytettävyyden tasoa.

Eräs merkittävä toteutuksen yksityiskohta Bashissa on se, että funktiot ovat ensiluokkaisia toimijoita; niillä ei ole erityistä määritysavaainsanaa kuten `function` muilla kielillä, vaikkakin `function` on Bashissa valinnainen luettavuuden vuoksi. Funktion skooppi on myös mielenkiintoinen – muuttujat ovat oletuksena globaaleja, ellei niitä ole määritelty paikallisiksi, mikä voi johtaa odottamattomaan käyttäytymiseen, jos sitä ei hallita asianmukaisesti.

## Katso myös
- Bash manuaali Shell-funktioista: https://www.gnu.org/software/bash/manual/html_node/Shell-Functions.html
- Kehittynyt Bash-skriptausopas: https://tldp.org/LDP/abs/html/functions.html
- "Pro Bash Programming: Scripting the GNU/Linux Shell" syvällisiin funktioiden skriptauskonsepteihin ja -käytäntöihin.
