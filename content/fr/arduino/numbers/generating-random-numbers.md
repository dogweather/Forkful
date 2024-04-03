---
date: 2024-01-27 20:32:41.674315-07:00
description: "G\xE9n\xE9rer des nombres al\xE9atoires dans les projets Arduino consiste\
  \ \xE0 produire des valeurs con\xE7ues pour \xEAtre impr\xE9visibles, ce qui est\
  \ crucial pour des\u2026"
lastmod: '2024-03-13T22:44:58.104765-06:00'
model: gpt-4-0125-preview
summary: "G\xE9n\xE9rer des nombres al\xE9atoires dans les projets Arduino consiste\
  \ \xE0 produire des valeurs con\xE7ues pour \xEAtre impr\xE9visibles, ce qui est\
  \ crucial pour des applications telles que les jeux, les simulations et les syst\xE8\
  mes de s\xE9curit\xE9."
title: "G\xE9n\xE9ration de nombres al\xE9atoires"
weight: 12
---

## Comment faire :
Arduino fournit des fonctions simples pour générer des nombres aléatoires : `randomSeed()` et `random()`. Pour commencer, initialisez le générateur de nombres aléatoires pour garantir différentes séquences de nombres à chaque exécution de votre programme. Une approche souvent utilisée consiste à initialiser avec une lecture analogique à partir d'une broche non connectée.

```Arduino
void setup() {
  Serial.begin(9600);
  // Initialiser le générateur aléatoire
  randomSeed(analogRead(0));
}

void loop() {
  // Générer un nombre aléatoire entre 0 et 99
  int randomNumber = random(100);
  Serial.println(randomNumber);
  delay(1000); // Délai d'une seconde pour la lisibilité de la sortie
}
```

Le programme ci-dessus initialise le générateur de nombres aléatoires dans la fonction `setup()` et génère un nouveau nombre entre 0 et 99 à chaque itération de la boucle, affichant le nombre dans le moniteur série.

Exemple de sortie :
```
42
17
93
...
```

## Exploration approfondie
La fonction `random()` d'Arduino utilise en arrière-plan un générateur de nombres pseudo-aléatoires (PRNG), qui suit une séquence déterministe mais qui semble statistiquement aléatoire. La valeur initiale, ou graine, de la séquence influence fortement son imprévisibilité, d'où l'utilisation courante de `randomSeed()` avec une entrée quelque peu aléatoire comme point de départ. Il est important de noter que l'aléatoire généré par Arduino est suffisant pour la plupart des projets de hobbyistes mais peut ne pas répondre aux critères des applications à haute sécurité en raison de sa prévisibilité dans le temps. Pour les fins cryptographiques, il est conseillé de se pencher sur des algorithmes plus sophistiqués et des générateurs de nombres aléatoires matériels (HRNGs), qui peuvent fournir une véritable aléatoire en utilisant des processus physiques.
