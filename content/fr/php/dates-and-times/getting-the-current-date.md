---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:10:12.960837-07:00
description: "Obtenir la date actuelle en PHP est une t\xE2che fondamentale qui vous\
  \ permet de r\xE9cup\xE9rer et de manipuler la date et l'heure du syst\xE8me. Cela\
  \ est crucial\u2026"
lastmod: '2024-03-13T22:44:57.890174-06:00'
model: gpt-4-0125-preview
summary: "Obtenir la date actuelle en PHP est une t\xE2che fondamentale qui vous permet\
  \ de r\xE9cup\xE9rer et de manipuler la date et l'heure du syst\xE8me."
title: Obtenir la date actuelle
weight: 29
---

## Comment faire :


### PHP Natif
La fonction intégrée `date()` de PHP est le moyen le plus direct d'obtenir la date actuelle. Vous pouvez formater la date de diverses manières en spécifiant le paramètre de format.

```php
echo date("Y-m-d"); // Sortie : 2023-04-01 (par exemple)
echo date("l, F j, Y"); // Sortie : Saturday, April 1, 2023
```

Pour obtenir la date et l'heure avec support du fuseau horaire, vous pouvez utiliser la classe `DateTime` avec `DateTimeZone`.

```php
$dateTime = new DateTime('now', new DateTimeZone('America/New_York'));
echo $dateTime->format('Y-m-d H:i:s'); // Sortie: 2023-04-01 12:00:00 (par exemple)
```

### Utilisation de Carbon (Une Bibliothèque Tierce Populaire)
[Carbon](https://carbon.nesbot.com/) est une extension simple de l'API pour `DateTime` qui fournit une manière plus propre et plus fluide de travailler avec les dates et les heures.

Tout d'abord, assurez-vous d'avoir Carbon installé via Composer :
```bash
composer require nesbot/carbon
```

Ensuite, vous pouvez l'utiliser pour obtenir la date actuelle :

```php
use Carbon\Carbon;

echo Carbon::now(); // Sortie : 2023-04-01 12:00:00 (par exemple, dans le format par défaut)
echo Carbon::now()->toDateString(); // Sortie : 2023-04-01
echo Carbon::now()->format('l, F j, Y'); // Sortie : Saturday, April 1, 2023
```

Carbon enrichit la gestion des dates et heures en PHP en ajoutant de la lisibilité et une abondance de fonctionnalités pour la manipulation, la comparaison et le formatage du temps.
