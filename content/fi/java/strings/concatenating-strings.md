---
date: 2024-01-20 17:34:54.818501-07:00
description: "Stringin yhdist\xE4minen eli konkatenointi tarkoittaa useampien tekstip\xE4\
  tkien yhdist\xE4mist\xE4 yhdeksi. Sit\xE4 k\xE4ytet\xE4\xE4n, koska halutaan rakentaa\
  \ dynaamisia\u2026"
lastmod: '2024-03-13T22:44:56.436734-06:00'
model: gpt-4-1106-preview
summary: "Stringin yhdist\xE4minen eli konkatenointi tarkoittaa useampien tekstip\xE4\
  tkien yhdist\xE4mist\xE4 yhdeksi."
title: "Merkkijonojen yhdist\xE4minen"
weight: 3
---

## How to: (Miten:)
Java tarjoaa useita tapoja yhdistää merkkijonoja. Tässä muutama esimerkki:

```java
// Käyttäen + operaattoria
String tervehdys = "Hei " + "maailma!";
System.out.println(tervehdys);  // Tulostuu: Hei maailma!

// StringBuilderin avulla
StringBuilder sb = new StringBuilder("Hei ");
sb.append("maailma!");
System.out.println(sb.toString());  // Tulostuu: Hei maailma!
```
Kumpikin tapa tuottaa saman lopputuloksen, mutta niiden käyttö voi vaihdella tilanteen mukaan.

## Deep Dive (Sukellus syvemmälle)
Konkatenoinnille on monta syytä, aivan kuten toteutustavallekin. Historiallisesti + -operaattoria on nähty usein, koska se on luettava ja helppo ymmärtää. Kuitenkin, jos yhdistetään monta merkkijonoa, `StringBuilder` on tehokkaampi, koska se ei luo joka välissä uutta merkkijonoa vaan rakentaa lopullisen merkkijonon pala palalta.

Aiemmissa Java-versioissa, kuten Java 5:ssa, `StringBuffer` oli suosittu, mutta se on synkronoitu ja siksi hitaampi kuin `StringBuilder`. Java 8 toi `String.join` -metodin, joka on käytännöllinen tietyissä tilanteissa.

Merkkijonojen yhdistäminen voi olla muistinkäytön kannalta kriittinen – jokainen merkkijonon yhdistäminen + -operaattorilla luo uuden merkkijono-olion, mikä voi johtaa muistin ylikuormitukseen suurissa sovelluksissa.

## See Also (Katso myös)
- Oracle's Java documentation on `StringBuilder`: https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html
- Effective Java by Joshua Bloch, specifically the item about String concatenation for more in-depth performance discussions.
- Stack Overflow discussions about when to use +, `StringBuilder`, or `StringBuffer`: https://stackoverflow.com
