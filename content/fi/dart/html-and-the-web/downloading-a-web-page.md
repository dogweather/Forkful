---
title:                "Web-sivun lataaminen"
date:                  2024-03-08T21:54:23.808748-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Mikä ja miksi?

Web-sivun lataaminen tarkoittaa web-sivun sisällön noutamista sen URL-osoitteen kautta käsittelyä tai tallennusta varten. Ohjelmoijat tekevät tämän tiedon poimimiseksi, muutosten seuraamiseksi tai sisällön arkistoimiseksi, mikä tekee siitä vakiomenetelmän web-kaapinnassa, data-louhinnassa ja automatisoiduissa testaustehtävissä.

## Kuinka:

Dart tarjoaa `http`-paketin, joka on suosittu kolmannen osapuolen kirjasto HTTP-pyyntöjen tekemiseen. Tässä on perusesimerkki siitä, kuinka sitä käytetään web-sivun lataamiseen:

Lisää ensin `http`-paketti `pubspec.yaml`-tiedostoosi:

```yaml
dependencies:
  http: ^0.13.3
```

Tämän jälkeen, tuo paketti ja käytä sitä web-sivun sisällön noutamiseen:

```dart
import 'package:http/http.dart' as http;

Future<void> main() async {
  var url = Uri.parse('http://example.com');
  var response = await http.get(url);
  if (response.statusCode == 200) {
    print('Sivu ladattu:');
    print(response.body);
  } else {
    print('Pyyntö epäonnistui statuksella: ${response.statusCode}.');
  }
}
```

**Esimerkkitulostus** (tämä vaihtelee web-sivun sisällön perusteella):

```
Sivu ladattu:
<!doctype html>
<html>
<head>
    <title>Esimerkki Domain</title>
...
</html>
```

Monimutkaisemmissa tilanteissa, kuten evästeiden käsittelyssä tai user-agent -otsakkeiden asettamisessa, käyttäisit samaa `http`-pakettia mutta lisäisit pyyntöösi lisäkonfiguraatioita:

```dart
import 'package:http/http.dart' as http;

Future<void> main() async {
  var headers = {
    'User-Agent': 'YourCustomUserAgent/1.0',
    'Cookie': 'nimi=arvo; nimi2=arvo2',
  };
  var url = Uri.parse('http://example.com');
  var response = await http.get(url, headers: headers);

  if (response.statusCode == 200) {
    print('Sivu ladattu mukautetuilla otsakkeilla:');
    print(response.body);
  } else {
    print('Pyyntö epäonnistui statuksella: ${response.statusCode}.');
  }
}
```

Tällaisten otsakkeiden käyttäminen voi matkia selaimen pyyntöjä tarkemmin, mikä on erityisen hyödyllistä, kun käsitellään sivustoja, joilla on erityisvaatimuksia tai suojausmekanismeja kaapimista vastaan.
