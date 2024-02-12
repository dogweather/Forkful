---
title:                "Conversion d'une chaîne de caractères en minuscules"
aliases:
- fr/ruby/converting-a-string-to-lower-case.md
date:                  2024-01-20T17:39:10.893538-07:00
model:                 gpt-4-1106-preview
simple_title:         "Conversion d'une chaîne de caractères en minuscules"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/ruby/converting-a-string-to-lower-case.md"
---

{{< edit_this_page >}}

## What & Why?
Convertir une chaîne de caractères en minuscules, c'est transformer tous ses caractères alphabétiques en leur équivalent minuscule. Les programmeurs le font pour uniformiser les données textuelles avant comparaison ou traitement, évitant ainsi les erreurs dues à la casse.

## How to:
```Ruby
# Exemple de base
phrase = "Bonjour, Monde!"
puts phrase.downcase
# => bonjour, monde!

# Utilisation dans une condition
if nom_utilisateur.downcase == "admin"
  puts "Accès autorisé"
else
  puts "Accès refusé"
end
```

## Deep Dive
En Ruby, `downcase` est une méthode intégrée pour les objets String, destinée à transformer les lettres majuscules en minuscules. Introduite dès les premières versions, c’est une méthode essential aujourd’hui pour le traitement de texte en Ruby.

Il y a des alternatives comme `downcase!`, qui modifie la chaîne de caractères sur place, ou `String#swapcase`, qui inverse la casse. La méthode `downcase` n'affecte pas les caractères non alphabetiques et prend en compte les règles de casse de la localisation par défaut du système, mais cela peut être limité pour certaines langues avec des règles de casse spécifiques.

D'un point de vue implémentation, `downcase` parcourt chaque caractère de la chaîne et vérifie s'il est en majuscule pour le convertir en minuscule. Cette opération est relativement simple mais peut avoir un impact sur les performances pour des très longues chaînes de caractères.

## See Also
- Ruby documentation pour `downcase`: [Ruby Doc - downcase](https://ruby-doc.org/core-3.1.0/String.html#method-i-downcase)
- Information sur les expressions régulières en Ruby, qui peuvent être utilisées pour la transformation de texte: [Ruby Doc - Regexp](https://ruby-doc.org/core-3.1.0/Regexp.html)
