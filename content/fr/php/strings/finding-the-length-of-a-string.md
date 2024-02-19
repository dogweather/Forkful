---
aliases:
- /fr/php/finding-the-length-of-a-string/
date: 2024-01-20 17:47:50.837566-07:00
description: "Trouver la longueur d'une cha\xEEne en PHP, c'est compter le nombre\
  \ de caract\xE8res qu'elle contient. Les programmeurs en ont besoin pour valider\
  \ des saisies,\u2026"
lastmod: 2024-02-18 23:09:08.912339
model: gpt-4-1106-preview
summary: "Trouver la longueur d'une cha\xEEne en PHP, c'est compter le nombre de caract\xE8\
  res qu'elle contient. Les programmeurs en ont besoin pour valider des saisies,\u2026"
title: "Trouver la longueur d'une cha\xEEne de caract\xE8res"
---

{{< edit_this_page >}}

## Quoi & Pourquoi?
Trouver la longueur d'une chaîne en PHP, c'est compter le nombre de caractères qu'elle contient. Les programmeurs en ont besoin pour valider des saisies, manipuler des textes ou pour tout simplement savoir où ils en sont.

## Comment faire :
```PHP
<?php
$texte = "Bonjour le monde!";
$longueur = strlen($texte); // La fonction native strlen()
echo $longueur; // Affiche 17
?>
```

```PHP
<?php
$phrase = "Vive PHP 8!";
$longueur = mb_strlen($phrase, 'UTF-8'); // Variante pour l'encodage multibyte
echo $longueur; // Affiche 10
?>
```

## Plongeon
Historiquement, `strlen()` était LA manière de mesurer la longueur d'une chaîne en PHP. Mais attention, `strlen()` compte les octets, pas les caractères. Avec l'arrivée de PHP 5.0.0, `mb_strlen()` a fait son entrée pour le support des encodages multioctets, comme UTF-8 où un caractère peut être composé de plusieurs octets. Alternativement, `grapheme_strlen()` est là pour les graphèmes Unicode. Pour les performances, `strlen()` gagne, mais pour la précision avec des textes variés, `mb_strlen()` est incontournable.

## À voir également
- La [documentation officielle de PHP sur strlen()](https://www.php.net/manual/fr/function.strlen.php)
- Un article sur la [gestion des encodages en PHP](https://www.php.net/manual/fr/mbstring.supported-encodings.php)
- La [fonction grapheme_strlen() sur PHP.net](https://www.php.net/manual/fr/function.grapheme-strlen.php)
