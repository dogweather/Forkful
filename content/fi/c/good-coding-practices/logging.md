---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:59:02.768262-07:00
description: "Lokitus C:ss\xE4 tarkoittaa ohjelman kulun ja merkitt\xE4vien tapahtumien\
  \ tallentamista sen suorituksen aikana, tarjoten konkreettisen katsauksen sen\u2026"
lastmod: '2024-03-13T22:44:57.047257-06:00'
model: gpt-4-0125-preview
summary: "Lokitus C:ss\xE4 tarkoittaa ohjelman kulun ja merkitt\xE4vien tapahtumien\
  \ tallentamista sen suorituksen aikana, tarjoten konkreettisen katsauksen sen k\xE4\
  ytt\xE4ytymiseen ja suorituskykyyn."
title: Lokitiedostot
weight: 17
---

## Kuinka:
C:ssä lokituksen voi saavuttaa perustiedostotoimintojen avulla tai käyttämällä monimutkaisempia kirjastoja. Aloittaaksemme yksinkertaisesti, aloitamme standardi I/O-kirjastosta. Seuraavat katkelmat esittelevät peruslokitusimplementaatioita.

Yksinkertaisten viestien lokitukseen:

```c
#include <stdio.h>

int main() {
    FILE *logFile;
    logFile = fopen("application.log", "a"); // Avaa lokitiedosto lisäystilassa
    
    if (logFile == NULL) {
        perror("Virhe avattaessa lokitiedostoa.");
        return -1;
    }
    
    fprintf(logFile, "Sovelluksen käynnistys.\n");
    
    // Sovelluslogiikkasi tässä
    
    fprintf(logFile, "Sovellus päättyi onnistuneesti.\n");
    fclose(logFile);
    
    return 0;
}
```

Tuloste `application.log`-tiedostossa:

```
Sovelluksen käynnistys.
Sovellus päättyi onnistuneesti.
```

Tarkempien lokien sisällyttäminen aikaleimoilla ja lokitasoilla:

```c
#include <stdio.h>
#include <time.h>

void logMessage(FILE *logFile, const char* taso, const char* viesti) {
    time_t nyt;
    time(&nyt);
    char* datetime = ctime(&nyt);
    datetime[strlen(datetime)-1] = '\0'; // Poista uudenviivan merkki
    fprintf(logFile, "[%s] %s - %s\n", datetime, taso, viesti);
}

int main() {
    FILE *logFile;
    logFile = fopen("detailed.log", "a");
    
    if (logFile == NULL) {
        perror("Virhe avattaessa lokitiedostoa.");
        return -1;
    }
    
    logMessage(logFile, "INFO", "Sovellus käynnistyy");
    // Sovelluslogiikkasi tässä
    logMessage(logFile, "ERROR", "Esimerkkivirhe");
    
    fclose(logFile);
    
    return 0;
}
```

Tuloste `detailed.log`-tiedostossa:

```
[To Mar 10 14:32:01 2023] INFO - Sovellus käynnistyy
[To Mar 10 14:32:02 2023] ERROR - Esimerkkivirhe
```

## Syväluotaus
Kuten osoitettu, lokitus C:ssä nojaa yksinkertaisiin tiedostotoimintoihin, mikä on tehokasta muttei yhtä voimakasta tai joustavaa kuin muiden kielten lokitusvälineet, kuten Pythonin `logging`-moduuli tai Javan `Log4j`. Lisäominaisuuksia vaativien lokituskykyjen saavuttamiseksi C:ssä kehittäjät kääntyvät usein kirjastojen, kuten Unix-tyylisten järjestelmien `syslog`, joka tarjoaa järjestelmänlaajuisen lokinhallinnan, tai kolmannen osapuolen kirjastojen kuten `log4c` puoleen.

Historiallisesti lokitus on ollut olennainen osa ohjelmointia, jäljittäen juurensa aikaisiin ohjelmointikäytäntöihin, jolloin ohjelman kulun ja virheiden seuranta ja ymmärtäminen tehtiin pääasiassa fyysisillä tulosteilla. Kuten järjestelmät kehittyivät, lokitus tuli monimutkaisemmaksi, tukien nykyään eri vakavuustasoja, lokin kiertoa ja asynkronista lokitusta.

Vaikka C:n standardikirjasto tarjoaa perustyökalut lokituksen toteuttamiseen, sen rajoitukset johtavat usein omien lokituskehikoiden luomiseen tai ulkoisten kirjastojen käyttöönottamiseen monipuolisempia ja joustavampia lokitusratkaisuja varten. Näistä rajoituksista huolimatta peruslokituksen ymmärtäminen ja toteuttaminen C:ssä on elintärkeää ohjelmiston vianetsinnän ja ylläpidon kannalta, erityisesti ympäristöissä, joissa ulkoiset riippuvuudet halutaan minimoida.
