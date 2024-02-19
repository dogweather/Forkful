---
aliases:
- /fi/arduino/removing-quotes-from-a-string/
date: 2024-01-26 03:37:05.556687-07:00
description: "Lainausmerkkien poistaminen merkkijonosta tarkoittaa yksitt\xE4isten\
  \ (`'`) tai kaksinkertaisten (`\"`) lainausmerkkien poistamista tekstin ymp\xE4\
  rilt\xE4.\u2026"
lastmod: 2024-02-18 23:09:07.887248
model: gpt-4-0125-preview
summary: "Lainausmerkkien poistaminen merkkijonosta tarkoittaa yksitt\xE4isten (`'`)\
  \ tai kaksinkertaisten (`\"`) lainausmerkkien poistamista tekstin ymp\xE4rilt\xE4\
  .\u2026"
title: Merkkijonosta lainausmerkkien poistaminen
---

{{< edit_this_page >}}

## Mitä & Miksi?
Lainausmerkkien poistaminen merkkijonosta tarkoittaa yksittäisten (`'`) tai kaksinkertaisten (`"`) lainausmerkkien poistamista tekstin ympäriltä. Ohjelmoijat tekevät tätä usein syötteen puhdistamiseksi, merkkijonojen vertailua varten tai tekstidataa käsiteltäessä, joka saattaa vahingossa sisältää lainausmerkkejä osana merkkijonoa.

## Miten:
Voit poistaa lainausmerkit merkkijonosta Arduinolla käymällä merkkijonon merkit läpi ja rakentamalla merkkijonon uudelleen ilman lainausmerkkejä. Esimerkiksi:

```arduino
String removeQuotes(String str) {
  String tulos = ""; // Luo tyhjä merkkijono tuloksen säilyttämiseen
  for (int i = 0; i < str.length(); i++) {
    if (str[i] != '"' && str[i] != '\'') { // Tarkista jokainen merkki
      tulos += str[i]; // Lisää tulosmerkkijonoon, jos ei ole lainausmerkki
    }
  }
  return tulos;
}

void setup() {
  Serial.begin(9600);
  String testStr = "'Hei, maailma!'";
  Serial.println(removeQuotes(testStr)); // Pitäisi tulostaa: Hei, maailma!
}

void loop() {
  // Ei mitään tehtävää täällä
}
```

Esimerkkitulostus sarjamonitorissa olisi:
```
Hei, maailma!
```

## Syväsukellus
Merkkijonoista merkkien poistaminen ei ole ainutlaatuista Arduinolle; se on yleistä monissa ohjelmointiympäristöissä. Historiallisesti merkkijonojen käsittelyfunktiot ovat olleet olennainen osa ohjelmointikieliä, jotta kehittäjät voivat puhdistaa ja jäsentää dataa tehokkaasti.

Manuaalisen silmukoinnin ja uuden merkkijonon rakentamisen lisäksi, kuten yllä näytettiin, on olemassa vaihtoehtoisia menetelmiä. Esimerkiksi voit käyttää `replace()`-metodia korvaamaan lainausmerkit tyhjällä merkkijonolla, vaikka siinä onkin kompromisseja luettavuuden ja pakomerkkien hallinnan suhteen.

```arduino
String removeQuotes(String str) {
  str.replace("\"", ""); // Korvaa kaikki kaksoislainausmerkit
  str.replace("\'", ""); // Korvaa kaikki yksittäiset lainausmerkit
  return str;
}
```

Vaihtoehtojen haittapuolien ymmärtäminen on tärkeää. Silmukkamenetelmä voi olla hitaampi pitkille merkkijonoille, mutta se on eksplisiittinen ja helppo mukauttaa (kuten jos tarvitsisit poistaa vain alku- ja loppulainausmerkit). `replace()`-metodi on tiiviimpi ja yleensä nopeampi, mutta siitä tulee hankalampaa, jos merkkijonossa on käsiteltävä paetut lainausmerkit.

## Katso myös
- Arduinon merkkijonoviite: https://www.arduino.cc/reference/en/language/variables/data-types/stringobject/
- W3Schoolsin opas C++ -merkkijonojen käsittelyyn (liittyy Arduinon kieleen): https://www.w3schools.com/cpp/cpp_strings.asp
- Stack Overflow -keskustelut C++ -merkkijonojen käsittelystä (Arduinon pohjakieli): https://stackoverflow.com/questions/tagged/string+cpp
