---
date: 2024-01-26 04:13:10.485438-07:00
description: "REPL, ou Boucle Lire-\xC9valuer-Afficher, est un environnement de programmation\
  \ permettant de tester dynamiquement le code Clojure pi\xE8ce par pi\xE8ce. Les\u2026"
lastmod: '2024-03-13T22:44:57.283855-06:00'
model: gpt-4-0125-preview
summary: "REPL, ou Boucle Lire-\xC9valuer-Afficher, est un environnement de programmation\
  \ permettant de tester dynamiquement le code Clojure pi\xE8ce par pi\xE8ce."
title: Utilisation d'une console interactive (REPL)
weight: 34
---

## Comment faire :
Commencez par lancer REPL :

```Clojure
user=> (println "Bonjour, REPL !")
Bonjour, REPL !
nil
```

Définissez une fonction et essayez-la :
```Clojure
user=> (defn greet [name] (str "Bonjour, " name "!"))
#'user/greet
user=> (greet "Programmeur Clojure")
"Bonjour, Programmeur Clojure !"
```

Expérimentez avec les structures de données :
```Clojure
user=> (def my-map {:a 1 :b 2})
#'user/my-map
user=> (assoc my-map :c 3)
{:a 1, :b 2, :c 3}
```

## Immersion Profonde
Le REPL est clé dans la philosophie de développement interactif de la famille Lisp, et Clojure, un dialecte Lisp moderne, tire grandement avantage de cet outil. Il remonte au premier REPL Lisp à la fin des années 1950. Parmi les alternatives dans d'autres langages figurent l'interpréteur Python et la console Node.js, mais le REPL de Clojure a un statut privilégié et est intégral au flux de travail.

Une session REPL Clojure peut être intégrée dans divers environnements tels que la ligne de commande, les IDE (comme IntelliJ avec Cursive, ou Emacs avec CIDER), ou des outils basés sur le navigateur comme Nightcode. Dans un sens plus profond, le REPL permet au développeur de manipuler les constructeurs du langage en temps d'exécution et de transporter les états à travers diverses transformations, menant souvent à la programmation exploratoire et à un code plus robuste.

La fonctionnalité du REPL est mise en évidence avec des outils comme `lein repl` ou `clj`, qui permettent la gestion des dépendances, divers plugins, et des personnalisations spécifiques au projet, conduisant à un processus de développement plus productif et flexible.

## Voir Aussi
- Le guide officiel du site Clojure sur le REPL : https://clojure.org/guides/repl/introduction
- La conférence de Rich Hickey sur le développement piloté par REPL : https://www.youtube.com/watch?v=Qx0-pViyIDU
- Clojure pratique : utiliser le REPL pour le développement itératif : http://practicalclj.blogspot.com/2009/10/using-clojure-repl.html
