---
title:                "Merkkijonon muuntaminen pieniksi kirjaimiksi"
aliases:
- /fi/c-sharp/converting-a-string-to-lower-case/
date:                  2024-01-20T17:38:04.359725-07:00
model:                 gpt-4-1106-preview
simple_title:         "Merkkijonon muuntaminen pieniksi kirjaimiksi"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/c-sharp/converting-a-string-to-lower-case.md"
---

{{< edit_this_page >}}

## What & Why? / Mikä ja miksi?
Muutetaan merkkijono pieniksi kirjaimiksi. Teemme sen siksi, että voimme vertailla tekstejä tasapuolisesti riippumatta alkuperäisestä kirjainkoosta tai toteuttaa ei-luokkauttavaa käyttäjäsyötteen käsittelyä.

## How to / Miten tehdään:
C# kielessä käytät `ToLower()`-metodia, joka on osa `String`-luokkaa. Tässä yksinkertainen esimerkki ja sen tulostus.

```C#
// Merkkijonon muuttaminen pieniksi kirjaimiksi
string originalText = "Hyvää Päivää!";
string lowerCaseText = originalText.ToLower();

Console.WriteLine(lowerCaseText);
```

Tulostus on:

```
hyvää päivää!
```

## Deep Dive / Syväsukellus:
Ennen .NET Frameworkia kehittäjät käyttivät usein C- tai C++-kirjastoja merkkijonojen käsittelyyn, joka oli työläämpää ja alttiimpaa virheille. `.ToLower()`-metodi on yksinkertaistanut prosessia huomattavasti. 

Kuitenkin metodin käytössä on otettava huomioon kielikohtaiset erityistapaukset. Esimerkiksi turkkilaisessa aakkostossa on pisteellinen ja pisteetön 'i', jotka vaativat kielikohtaista käsittelyä. C# käyttää kulttuurikohtaisia asetuksia (`CultureInfo`), jos halutaan ottaa huomioon eri kieltä puhuvien käyttäjien tarpeet.

Vaihtoehtoisesti, jos haluat varmistaa, että käytät "invarianttia kulttuuria" (kulttuurista riippumatonta), voit käyttää `ToLowerInvariant()`-metodia:

```C#
string invariantLowerCaseText = originalText.ToLowerInvariant();
```

Toinen huomionarvoinen asia on suorituskyky. Suuremmille tekstipaljouksille suorituskyky saattaa laskea, joten kannattaa harkita metodin kutsukertojen minimoimista.

## See Also / Katso myös:
- C# dokumentaatio `String.ToLower()`: https://docs.microsoft.com/dotnet/api/system.string.tolower
- C# dokumentaatio `String.ToLowerInvariant()`: https://docs.microsoft.com/dotnet/api/system.string.tolowerinvariant
- C# dokumentaatio kulttuuritietoisuudesta (`CultureInfo`): https://docs.microsoft.com/dotnet/api/system.globalization.cultureinfo
- Tietoa suorituskyvystä ja optimoinnista: https://docs.microsoft.com/dotnet/standard/base-types/best-practices-strings
