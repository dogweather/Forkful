---
title:                "Merkkijonon muuttaminen isoiksi kirjaimiksi"
aliases:
- fi/c-sharp/capitalizing-a-string.md
date:                  2024-02-03T19:05:20.707397-07:00
model:                 gpt-4-0125-preview
simple_title:         "Merkkijonon muuttaminen isoiksi kirjaimiksi"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/c-sharp/capitalizing-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Mikä & Miksi?
Merkkijonon alkukirjaimen muuttaminen isoksi C#:ssa tarkoittaa merkkijonon ensimmäisen merkin muuttamista isoksi kirjaimeksi, jos se ei jo ole. Tämä muutos voi olla ratkaisevan tärkeä tulosteiden muotoilussa, koodausstandardien noudattamisessa tai käyttöliittymätekstien luettavuuden parantamisessa.

## Kuinka:
C# tarjoaa suoraviivaisen tavan muuttaa merkkijonojen alkukirjaimet isoiksi sisäänrakennettuja metodeja käyttäen. Yksinkertaisin tapa saavuttaa tämä on muokata merkkijonoa suoraan näiden metodien avulla. Monimutkaisempia tai tiettyjä pääomitusvaatimuksia varten (esim. jokaisen sanan alkukirjain isoksi) saattaa olla tarpeen käyttää lisäkirjastoja tai manuaalisia metodeja. Alla on esimerkkejä, jotka osoittavat, kuinka merkkijonoja voidaan muuttaa eri tavoin C#:ssa isoksi.

### Perusmuotoilu:
Yhden sanan tai lauseen ensimmäisen kirjaimen muotoilu:

```csharp
string originalString = "hello world";
string capitalizedString = char.ToUpper(originalString[0]) + originalString.Substring(1);
Console.WriteLine(capitalizedString); // Tuloste: "Hello world"
```

### Jokaisen sanan alkukirjaimen muotoilu:
Jos haluat muuttaa jokaisen sanan ensimmäisen kirjaimen isoksi merkkijonossa, voit käyttää `TextInfo.ToTitleCase` -metodia, joka löytyy `System.Globalization` -nimiavaruudesta:

```csharp
using System;
using System.Globalization;

string originalString = "hello world";
TextInfo textInfo = CultureInfo.CurrentCulture.TextInfo;
string capitalizedString = textInfo.ToTitleCase(originalString);
Console.WriteLine(capitalizedString); // Tuloste: "Hello World"
```

Huomautus: `ToTitleCase` ei muuta loppukirjaimia pieniksi; se muuttaa vain jokaisen sanan ensimmäisen kirjaimen isoksi. Lisäksi tietyt sanat otsikkokirjoituksen säännöissä (kuten "and", "or", "of") eivät välttämättä tule muutetuiksi isoksi riippuen kulttuuriasetuksista.

### Laajennusmetodien käyttö uudelleenkäytettävyyden parantamiseksi:
Voit luoda `string`-luokalle laajennusmetodin, jotta pääomitusprosessin yksinkertaistamiseksi tekemäsi koodista saadaan siistimpi ja uudelleenkäytettävämpi. Näin luot ja käytät tällaista metodia:

```csharp
using System;

public static class StringExtensions
{
    public static string Capitalize(this string input)
    {
        if (string.IsNullOrEmpty(input))
        {
            return input;
        }
        return char.ToUpper(input[0]) + input.Substring(1);
    }
}

class Program
{
    static void Main(string[] args)
    {
        string originalString = "hello world";
        string capitalizedString = originalString.Capitalize();
        Console.WriteLine(capitalizedString); // Tuloste: "Hello world"
    }
}
```

Tätä laajennusmetodia `Capitalize` voidaan kutsua mille tahansa merkkijonolle nimiavaruuden sisällä, tarjoten intuitiivisemman ja oliopohjaisemman lähestymistavan merkkijonokäsittelyyn C#-kielellä.

### Kolmannen osapuolen kirjastot:
Vaikka C#-standardikirjasto kattaa suurimman osan tarpeista merkkijonojen tai jokaisen sanan alkukirjainmuutoksen suhteen, tietyt erikoistehtävät saattavat hyötyä kolmannen osapuolen kirjastoista, kuten Humanizer. Kuitenkin yksinkertaisten merkkijonojen tai jokaisen sanan pääomituksen tehtävässä C#-standardimetodit ovat riittäviä ja tehokkaita, mikä poistaa tarpeen ulkoisille riippuvuuksille.
