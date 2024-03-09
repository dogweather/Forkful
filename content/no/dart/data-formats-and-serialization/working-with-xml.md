---
title:                "Arbeider med XML"
date:                  2024-03-08T21:57:43.410385-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Hva & Hvorfor?

Å jobbe med XML i Dart innebærer parsing, spørre og modifisere XML-dokumenter, en prosess som er avgjørende for applikasjoner som samhandler med webtjenester, konfigurasjonsfiler eller arvesystemer. Programmerere gjør dette for å muliggjøre datautveksling, konfigurasjoner eller til og med fjernprosedyrekall i et strukturert, hierarkisk format som er både menneskelesbart og maskinparbart.

## Hvordan:

Dart inkluderer ikke innebygget støtte for XML-håndtering i sitt standardbibliotek, noe som nødvendiggjør bruk av tredjepartspakker. En populær pakke er `xml`. For å bruke den, må du først legge den til i `pubspec.yaml`:

```yaml
dependencies:
  xml: ^5.0.0 // Bruk den nyeste versjonen tilgjengelig
```

Deretter, importer pakken i Dart-filen din:

```dart
import 'package:xml/xml.dart' as xml;
```

**Parse XML:**

Anta at du har en XML-streng som denne:

```xml
<String name="greeting">Hello, world!</String>
```

Du kan parse og lese XML-en slik:

```dart
void parseXml(String xmlString) {
    final document = xml.XmlDocument.parse(xmlString);
    final String content = document.findElements('String').single.getAttribute('name');
    print(content); // Utganger: greeting
}

void main() {
  final xmlString = '<String name="greeting">Hello, world!</String>';
  parseXml(xmlString);
}
```

**Opprette XML-dokumenter:**

Å opprette et nytt XML-dokument er enkelt med `xml`-pakken:

```dart
void createXml() {
  final builder = xml.XmlBuilder();
  builder.processing('xml', 'version="1.0"');
  builder.element('greeting', nest: () {
    builder.attribute('name', 'hello');
    builder.text('Hello, world!');
  });
  final xmlDocument = builder.buildDocument();
  print(xmlDocument.toXmlString(med_pent: true));
}

void main() {
  createXml();
}
```

**Utdata**:

```xml
<?xml version="1.0"?>
<greeting name="hello">Hello, world!</greeting>
```

**Spørre og Modifisere XML:**

For å finne eller modifisere elementer, kan du bruke XPath-lignende metoder:

```dart
void modifyXml(String xmlString) {
    var document = xml.XmlDocument.parse(xmlString);
    var greeting = document.findAllElements('greeting').first;
    
    // Modifiserer 'name'-attributtet
    greeting.setAttribute('name', 'greeting_modified');
    
    // Legger til et nytt barneelement
    greeting.children.add(xml.XmlElement(xml.XmlName('message'), [], [xml.XmlText('Goodbye!')]));
    
    print(document.toXmlString(med_pent: true));
}

void main() {
  final xmlString = '<greeting name="hello">Hello, world!</greeting>';
  modifyXml(xmlString);
}
```

**Utdata**:

```xml
<greeting name="greeting_modified">
  Hello, world!
  <message>Goodbye!</message>
</greeting>
```

Disse eksemplene demonstrerer grunnleggende operasjoner for å jobbe med XML i Dart. Med `xml`-pakken kan du parse, opprette og manipulere XML-dokumenter for å møte applikasjonskravene dine.
