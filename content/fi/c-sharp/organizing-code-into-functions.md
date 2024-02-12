---
title:                "Koodin järjestäminen funktioihin"
aliases:
- fi/c-sharp/organizing-code-into-functions.md
date:                  2024-01-26T01:09:44.095505-07:00
model:                 gpt-4-1106-preview
simple_title:         "Koodin järjestäminen funktioihin"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/c-sharp/organizing-code-into-functions.md"
---

{{< edit_this_page >}}

## Mikä & Miksi?
Koodin jäsenteleminen funktioiksi on kuin LEGO-palikoiden lajitteleminen bokseihin—se tekee niiden löytämisestä ja käytöstä helpompaa. Tämä tehdään toiston välttämiseksi, ymmärtämisen yksinkertaistamiseksi ja ylläpidon päänsäryn vähentämiseksi.

## Kuinka:
Kuvittele, että sinulla on koodia, joka tulostaa tervehdyksen useita kertoja. Ilman funktioita se on sotkuinen. Funktioilla se on siisti.

```C#
// Ilman funktioita - toistuvaa
Console.WriteLine("Hello, Amy!");
Console.WriteLine("Hello, Bob!");
Console.WriteLine("Hello, Charlie!");

// Funktioilla - siistimpää
void Greet(string name) {
    Console.WriteLine($"Hello, {name}!");
}

Greet("Amy");
Greet("Bob");
Greet("Charlie");
```

Tuloste on sama, mutta toinen versio on paljon siistimpi.

## Syväsukellus
Kauas taakse, assembly-kielen päiviin, hyppäisit eri koodikohtiin GOTO-komennolla—kaoottista ja vaikeasti seurattavaa. Funktiot ovat merkittävä tasoparannus, kuin järjestetyt laatikot työkalupakissa. Vaihtoehtoja? Tietysti. On metodeja, jotka ovat funktioita luokkakontekstissa. Sitten on lambda-lausekkeet ja inline-funktiot nopeita, kertakäyttöisiä tehtäviä varten.

Toteutuksesta—pienet, fokusoituneet funktiot ovat kultaa. Ne ovat helpompia testata ja debugata. Suuret funktiot, joilla on monta vastuuta, voivat muuttua hirviömäisiksi, ansaiten epäilyttävän tittelin "spagettikoodi". Pidä yksi tehtävä per funktio; kiität itseäsi myöhemmin.

## Katso Myös
Lisää funktioista ja parhaista käytännöistä, tutustu:

- Clean Code by Robert C. Martin: Periaatteet pitääksesi funktiosi siistinä.
- Refactoring by Martin Fowler: Tavat parantaa olemassa olevaa koodia.
- Microsoft C# Guide on Methods: https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/methods
