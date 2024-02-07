---
title:                "Convertir une chaîne en minuscules"
date:                  2024-02-03T17:54:30.086073-07:00
model:                 gpt-4-0125-preview
simple_title:         "Convertir une chaîne en minuscules"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/c/converting-a-string-to-lower-case.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?

Convertir une chaîne en minuscules en C implique de transformer toutes les lettres majuscules d'une chaîne donnée en leurs équivalents en minuscules. Les programmeurs effectuent souvent cette opération pour standardiser la saisie de texte pour la comparaison, les opérations de recherche, ou simplement pour une cohérence esthétique dans la sortie.

## Comment :

C n'a pas de fonction intégrée pour la conversion de chaîne en minuscules directement, contrairement à certains langages de haut niveau. Cependant, le processus peut être facilement mis en œuvre en utilisant les fonctions de la bibliothèque standard C. Ci-dessous, un guide étape par étape et un exemple illustrant comment convertir une chaîne en minuscules.

```c
#include <stdio.h>
#include <ctype.h>

void toLowerCase(char *str) {
    while (*str) {
        *str = tolower(*str);
        str++;
    }
}

int main() {
    char text[] = "Hello, World!";
    printf("Original : %s\n", text);

    toLowerCase(text);
    printf("Minuscules : %s\n", text);

    return 0;
}
```

**Exemple de sortie :**

```
Original : Hello, World!
Minuscules : hello, world!
```

Dans cet exemple, la fonction `toLowerCase` itère à travers chaque caractère de la chaîne d'entrée, le convertissant en son équivalent en minuscules à l'aide de la fonction `tolower` de `ctype.h`. La modification est faite sur place, modifiant la chaîne originale.

## Approfondissement

La fonction `tolower` utilisée dans l'exemple ci-dessus fait partie de la bibliothèque standard C, spécifiquement dans le fichier d'en-tête `ctype.h`. Elle fonctionne en fonction de la locale courante, mais pour la locale standard "C", elle gère l'ensemble de caractères ASCII où de 'A' à 'Z' sont convertis en 'a' à 'z'.

Historiquement, le traitement de l'encodage des caractères et de la conversion des cas en C était étroitement lié à l'ensemble de caractères ASCII, limitant son utilité dans les applications internationales ou localisées où les caractères hors ASCII sont courants. Les langages de programmation modernes pourraient offrir des méthodes de chaîne intégrées pour effectuer la conversion de cas en tenant compte de la locale et des caractères Unicode, ce que C manque nativement.

Dans des scénarios nécessitant une manipulation extensive de texte, en particulier avec des caractères non ASCII, les programmeurs pourraient envisager d'utiliser des bibliothèques offrant une meilleure prise en charge de l'internationalisation, telles que ICU (International Components for Unicode). Cependant, pour la plupart des applications traitant du texte ASCII, l'approche démontrée est efficace et simple. Elle met en évidence la propension de C à donner aux programmeurs le contrôle sur la manipulation des données, bien qu'un peu plus de travail soit impliqué par rapport aux langages de niveau supérieur.
