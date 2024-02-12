---
title:                "Retirer les guillemets d'une chaîne"
aliases:
- /fr/php/removing-quotes-from-a-string/
date:                  2024-01-26T03:40:38.024667-07:00
model:                 gpt-4-0125-preview
simple_title:         "Retirer les guillemets d'une chaîne"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/php/removing-quotes-from-a-string.md"
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?
Enlever les guillemets d'une chaîne en PHP signifie retirer ces caractères de guillemets doubles (`"`) ou simples (`'`) qui peuvent perturber la logique de votre code ou vos requêtes de base de données. Les programmeurs le font pour nettoyer ou assainir les données d'entrée, garantissant que les chaînes sont utilisées ou stockées en toute sécurité.

## Comment faire :
Voici un exemple simple utilisant les fonctions intégrées de PHP :

```php
$quotedString = "'Bonjour,' dit-elle, \"C'est une belle journée !\"";
$unquotedString = str_replace(array("'", "\""), '', $quotedString);
echo $unquotedString; // Affiche : Bonjour, dit-elle, Cest une belle journée !
```

Simple, n'est-ce pas ? Cette fonction `str_replace()` prend un tableau de caractères à retirer de la chaîne, incluant à la fois les guillemets simples et doubles.

## Approfondissement
Au tout début de PHP, les développeurs devaient être particulièrement prudents avec les guillemets dans les chaînes, surtout lors de l'insertion des données dans une base de données. Des guillemets mal gérés pouvaient conduire à des attaques par injection SQL. C'est là qu'entraient en jeu les guillemets magiques, une fonctionnalité qui échappait automatiquement les données d'entrée. Elle est devenue obsolète et a finalement été supprimée car elle encourait de mauvaises pratiques de codage et des problèmes de sécurité.

Aujourd'hui, nous utilisons des fonctions comme `str_replace()` ou des expressions régulières avec `preg_replace()` pour des motifs plus avancés. Voici un exemple avec une expression régulière :

```php
$quotedString = "'Bonjour,' dit-elle, \"C'est une belle journée !\"";
$unquotedString = preg_replace('/[\'"]/', '', $quotedString);
echo $unquotedString;
```

Pour les données JSON, vous pourriez utiliser `json_encode()` avec des options comme `JSON_UNESCAPED_SLASHES | JSON_UNESCAPED_UNICODE` pour éviter des barres obliques supplémentaires dans vos guillemets.

Lors de l'implémentation, considérez les cas limites. Que se passe-t-il si votre chaîne est censée avoir certains guillemets, comme des dialogues dans une histoire ou des pouces dans des mesures ? Le contexte compte, alors adaptez votre suppression de guillemets à l'utilisation prévue des données.

## Voir Aussi
- [PHP : str_replace](https://www.php.net/manual/fr/function.str-replace.php)
- [PHP : preg_replace](https://www.php.net/manual/fr/function.preg-replace.php)
- [PHP : json_encode](https://www.php.net/manual/fr/function.json-encode.php)
- [OWASP : Prévention d'injection SQL](https://owasp.org/www-community/attacks/SQL_Injection)
