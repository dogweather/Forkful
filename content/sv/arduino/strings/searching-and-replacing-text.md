---
date: 2024-01-20 17:57:07.512304-07:00
description: "S\xF6kning och ers\xE4ttning av text inneb\xE4r att man automatiskt\
  \ hittar specifika str\xE4ngar och byter ut dem mot andra. Programmerare anv\xE4\
  nder detta f\xF6r att\u2026"
lastmod: '2024-03-13T22:44:38.153339-06:00'
model: gpt-4-1106-preview
summary: "S\xF6kning och ers\xE4ttning av text inneb\xE4r att man automatiskt hittar\
  \ specifika str\xE4ngar och byter ut dem mot andra."
title: "S\xF6kning och ers\xE4ttning av text"
weight: 10
---

## Så här gör du:
Följande Arduino-kod använder `String.replace()` för att söka och ersätta text.

```arduino
void setup() {
  Serial.begin(9600);

  String text = "Hej världen!";
  Serial.println("Original text: " + text);

  text.replace("världen", "Arduino");
  Serial.println("Efter ersättning: " + text);
}

void loop() {
  // Vi behöver inte köra något i loop-funktionen för detta exempel.
}
```

Exempel på output:

```
Original text: Hej världen!
Efter ersättning: Hej Arduino!
```

## Djupdykning
Sök-och-ersätt-funktionen har rötter i tidiga textredigeringsprogram från 1970-talet, till exempel `ed` och dess efterföljare `sed` i Unix. I Arduino kan `String`-objekt hantera grundläggande sök-och-ersätt-operationer genom inbyggda metoder som `.replace()`. För mer komplicerade situationer, som stora textmängder eller dynamisk textmanipulering, kan man behöva använda alternativa tillvägagångssätt som t.ex. buffertar och tecken-för-tecken bearbetning. När man implementerar sök-och-ersätt överväg prestanda och tillgängligt minne, speciellt på en minnesbegränsad plattform som Arduino.

## Se även
- Arduino String Reference: https://www.arduino.cc/reference/en/language/variables/data-types/stringobject/
- `ed` text editor: https://en.wikipedia.org/wiki/Ed_(text_editor)
- `sed` stream editor: https://en.wikipedia.org/wiki/Sed
