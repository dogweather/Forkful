---
title:                "Het huidige datum ophalen"
aliases:
- /nl/php/getting-the-current-date/
date:                  2024-01-28T22:01:06.215032-07:00
model:                 gpt-4-0125-preview
simple_title:         "Het huidige datum ophalen"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/php/getting-the-current-date.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
De huidige datum in PHP verkrijgen draait allemaal om het plukken van de datum en tijd van vandaag direct vanaf de server. Programmeurs doen dit om de acties van gebruikers te volgen, berichten te timestampen, of gewoon om te zeggen: "Hé, het is vrijdag!"

## Hoe:
Je roept de huidige datum in PHP op met de `date()` functie. Bijvoorbeeld:

```PHP
echo "De datum van vandaag is: " . date("Y-m-d") . "<br>";
echo "De tijd is: " . date("h:i:sa");
```

De output kan zijn:
```
De datum van vandaag is: 2023-04-01
De tijd is: 10:15:36am
```

Simpel, toch? Voor UTC-tijd gebruik je de `gmdate()` functie:

```PHP
echo "UTC-tijd is: " . gmdate("h:i:sa");
```

Bam, je krijgt zoiets als:
```
UTC-tijd is: 02:15:36pm
```

## Diepe Duik
Nu we de basis hebben geplukt, laten we een beetje in de grond graven. Ten eerste, onder de motorkap, gebruikt PHP de systeemklok van de server voor zijn tijdfuncties. Denkend aan vroeger, hebben PHP's datumfuncties een lange geschiedenis, afkomstig van Unix's manier van omgaan met data en tijden.

Voor `date()` had je `strtotime()` en `mktime()`. Deze oudjes vertalen zo ongeveer elke Engelse tekstuele datumtijd beschrijving naar een Unix-timestamp. Maar ze zijn omslachtiger voor een snelle huidige tijdgreep.

Nu, voor de nerdy bits – PHP slaat datums op als gehele getallen. Specifiek, seconden sinds het Unix-tijdperk (1 januari 1970). Dit betekent dat het universum volgens PHP in 2038 kaboom gaat (Google "Jaar 2038 probleem" voor de details van de doomsday). Momenteel is dit geen probleem, aangezien PHP 7 en nieuwer 64-bits integers gebruiken, waardoor we tijd hebben... nou ja, bijna tot het einde der tijden.

Tijdzones—deze kunnen met je tijden knoeien als je niet voorzichtig bent. Stel je standaardtijdzone in met `date_default_timezone_set()` als je wilt synchroniseren met een specifiek horloge.

## Zie Ook
Hier zijn enkele nuttige dokken en tutorials om dieper in te duiken:
- [Documentatie van PHP's date functie](https://www.php.net/manual/en/function.date.php)
- [Tijdzones in PHP](https://www.php.net/manual/en/timezones.php)
- [PHP DateTime-klasse](https://www.php.net/manual/en/class.datetime.php), voor chiquere manieren om met data en tijden om te gaan
- Dat naderende [Jaar 2038 probleem](https://en.wikipedia.org/wiki/Year_2038_problem)
