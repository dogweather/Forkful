---
changelog:
- 2024-01-30, gpt-4-0125-preview, translated from English
date: 2024-01-30 19:10:11.601710-07:00
description: "I Arduino-verdenen lar assoiative matriser deg pare n\xF8kler med verdier,\
  \ litt som \xE5 matche sokker med deres par. De er et f\xF8rstevalg n\xE5r du trenger\
  \ \xE5 lagre\u2026"
lastmod: '2024-03-13T22:44:41.051736-06:00'
model: gpt-4-0125-preview
summary: "I Arduino-verdenen lar assoiative matriser deg pare n\xF8kler med verdier,\
  \ litt som \xE5 matche sokker med deres par."
title: Bruke associative tabeller
weight: 15
---

## Hvordan:
Arduino, strengt tatt, har ikke innebygd støtte for assoiative matriser slik du ville funnet i høyere programmeringsspråk. Men, frykt ikke. Vi kan være kreative ved å bruke strukturer og matriser for å etterligne denne funksjonaliteten. Her er et enkelt eksempel på å lage en grunnleggende "assosiativ matrise" for lagring og tilgang til temperaturer for forskjellige byer.

Først, definer en struktur for å holde byen (nøkkel) og dens temperatur (verdi):

```cpp
struct CityTemperature {
  String city;
  float temperature;
};
```

Deretter, initialiser en matrise av `CityTemperature` objekter:

```cpp
CityTemperature temperatures[] = {
  {"New York", 19.5},
  {"Los Angeles", 22.0},
  {"Chicago", 17.0}
};
```

Slik kan du få tilgang til og vise temperaturen for en spesifikk by:

```cpp
void setup() {
  Serial.begin(9600);
  for(int i = 0; i < 3; i++) {
    if(temperatures[i].city == "Los Angeles") {
      Serial.print("Temperaturen i Los Angeles er: ");
      Serial.println(temperatures[i].temperature);
    }
  }
}

void loop() {
  // Ingenting her for nå.
}
```

Å kjøre denne koden vil gi deg utskriften:

```
Temperaturen i Los Angeles er: 22.0
```

## Dypdykk
Historisk sett kom programmeringsspråk som C og C++ (som Arduino-syntaksen er avledet fra) ikke med innebygde assoiative matriser, noe som førte til løsninger som den vist ovenfor. Denne tilnærmingen er relativt enkel, men skalerer dårlig etter hvert som datamengden øker på grunn av dens O(n) opptid.

Språk som Python tilbyr ordbøker, og JavaScript har objekter for dette formålet, begge er langt mer effektive for å håndtere nøkkel-verdipar. I Arduino, når ytelse og effektivitet blir kritisk, kan utviklere velge mer spesialiserte datatstrukturer, som hashtabeller, implementert via biblioteker.

Selv om Arduino ikke støtter assoiative matriser nativt, har fellesskapet utviklet biblioteker som `HashMap` som kan legges til prosjektet ditt for å tilby lignende funksjonalitet med bedre ytelse enn en gjør-det-selv-tilnærming. Disse bibliotekene tilbyr vanligvis en mer elegant og effektiv måte å håndtere assoiative matriser på, spesielt for mer komplekse prosjekter.
