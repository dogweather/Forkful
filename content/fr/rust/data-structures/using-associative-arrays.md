---
title:                "Utilisation des tableaux associatifs"
aliases:
- /fr/rust/using-associative-arrays/
date:                  2024-01-30T19:12:43.559000-07:00
model:                 gpt-4-0125-preview
simple_title:         "Utilisation des tableaux associatifs"

tag:                  "Data Structures"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/rust/using-associative-arrays.md"
changelog:
  - 2024-01-30, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?

Les tableaux associatifs, ou ce que les Rustacés appellent "hash maps", sont des collections qui stockent des données en paires clé-valeur. Les programmeurs les utilisent pour une recherche rapide de données, permettant une manipulation efficace des données basée sur des clés uniques.

## Comment faire :

En Rust, le type `HashMap` du module `std::collections` fournit la fonctionnalité des tableaux associatifs. Voici comment vous pouvez travailler avec eux :

```Rust
use std::collections::HashMap;

fn main() {
    // Création d'un nouveau HashMap
    let mut scores = HashMap::new();

    // Insertion de valeurs
    scores.insert(String::from("Blue"), 10);
    scores.insert(String::from("Yellow"), 50);

    // Accès aux valeurs
    let team_name = String::from("Blue");
    if let Some(score) = scores.get(&team_name) {
        println!("Score pour l'équipe Blue: {}", score); // Sortie: Score pour l'équipe Blue: 10
    }

    // Mise à jour d'une valeur
    scores.entry(String::from("Blue")).and_modify(|e| *e += 5);

    // Itération sur les paires clé-valeur
    for (key, value) in &scores {
        println!("{}: {}", key, value); // Sortie: Blue: 15, Yellow: 50
    }
}
```

## Approfondissement

Le `HashMap` en Rust utilise une fonction de hachage pour mapper les clés aux valeurs, ce qui permet une récupération rapide des données. Cependant, cette efficacité a un coût : les hash maps ne maintiennent pas l'ordre de leurs éléments. Cela contraste avec d'autres implémentations de tableaux associatifs, comme ceux en Python (`dict`) ou en Ruby, qui, dans les versions récentes, maintiennent l'ordre d'insertion comme une fonctionnalité. Pour les cas d'utilisation où l'ordre des paires clé-valeur est significatif, les développeurs Rust pourraient envisager d'utiliser le `BTreeMap` du module `std::collections`, qui maintient l'ordre mais peut offrir une insertion et une récupération plus lentes par rapport à `HashMap`. En fin de compte, le choix entre `HashMap` et `BTreeMap` dépend des exigences spécifiques concernant l'ordre et la performance.
