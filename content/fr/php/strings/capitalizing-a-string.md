---
title:                "Mettre en majuscule une chaîne"
aliases:
- /fr/php/capitalizing-a-string/
date:                  2024-02-03T19:05:52.245010-07:00
model:                 gpt-4-0125-preview
simple_title:         "Mettre en majuscule une chaîne"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/php/capitalizing-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?
Mettre en majuscule une chaîne implique de modifier le premier caractère d'un texte donné en majuscule, afin que les phrases, les titres ou les noms propres commencent correctement dans un ensemble de données. Les programmeurs exécutent souvent la capitalisation de chaînes pour normaliser les données, améliorer la lisibilité ou assurer la cohérence dans la saisie utilisateur ou le traitement de données textuelles.

## Comment faire :
PHP prend en charge nativement diverses fonctions pour mettre en majuscule les chaînes, chacune servant un objectif différent. Voici comment vous pouvez les utiliser :

### Mettre en majuscule la première lettre d'une chaîne :

```php
$string = "bonjour, monde !";
$capitalizedString = ucfirst($string);
echo $capitalizedString; // Affiche : Bonjour, monde !
```

### Mettre en majuscule la première lettre de chaque mot :

```php
$string = "bonjour, monde !";
$capitalizedWords = ucwords($string);
echo $capitalizedWords; // Affiche : Bonjour, Monde !
```

### Convertir toute la chaîne en majuscules :

```php
$string = "bonjour, monde !";
$upperCaseString = strtoupper($string);
echo $upperCaseString; // Affiche : BONJOUR, MONDE !
```

Pour les scénarios nécessitant plus de personnalisation ou des solutions tierces, des bibliothèques comme `mbstring` (pour les chaînes multioctets) peuvent être utilisées, en particulier lorsqu'il s'agit d'internationalisation où les caractères peuvent aller au-delà de l'ensemble de caractères ASCII de base.

### Utiliser mbstring pour mettre en majuscule les chaînes UTF-8 :

Assurez-vous que l'extension `mbstring` est activée dans votre configuration PHP, puis :

```php
$string = "élégant";
$capitalizedString = mb_convert_case($string, MB_CASE_TITLE, "UTF-8");
echo $capitalizedString; // Affiche : Élégant
```

Cette approche aide à mettre en majuscule avec précision les chaînes qui incluent des caractères non-ASCII, en respectant les nuances de diverses langues.
