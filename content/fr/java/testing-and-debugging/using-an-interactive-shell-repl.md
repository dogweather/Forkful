---
title:                "Utilisation d'une console interactive (REPL)"
date:                  2024-01-26T04:15:29.887583-07:00
model:                 gpt-4-0125-preview
simple_title:         "Utilisation d'une console interactive (REPL)"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/java/using-an-interactive-shell-repl.md"
---

{{< edit_this_page >}}

## Quoi et pourquoi ?
Un REPL (Read-Eval-Print Loop, boucle de lecture, évaluation et impression) est un shell interactif qui traite des entrées utilisateur uniques, exécute du code et renvoie le résultat. Les programmeurs l'utilisent pour des expériences rapides, du débogage ou pour l'apprentissage, car il permet un retour immédiat et une itération.

## Comment faire :
Démarrer un REPL en Java est simple avec l'outil `jshell` introduit dans Java 9. Voici comment mettre la main dessus et lancer une session de base :

```Java
jshell> int sum(int a, int b) {
   ...> return a + b;
   ...> }
|  méthode sum(int,int) créée

jshell> sum(5, 7)
$1 ==> 12
```

Quittez à tout moment avec `/exit`.

```Java
jshell> /exit
|  Au revoir
```

## Plongée profonde
Avant `jshell`, les programmeurs Java n'avaient pas de REPL officiel, contrairement aux développeurs Python ou Ruby. Ils utilisaient des IDE ou écrivaient des programmes complets même pour des tâches triviales. `jshell` a été un changement de jeu à partir de Java 9, comblant cette lacune.

Les alternatives incluent les compilateurs en ligne ou les plugins d'IDE, mais ils ne rivalisent pas avec l'immédiateté de `jshell`. En ce qui concerne les mécanismes internes, `jshell` utilise l'API du compilateur Java pour exécuter des fragments de code, ce qui est plutôt soigné. C'est plus qu'un terrain de jeu - il peut importer des bibliothèques, définir des classes, et plus encore. Cela en fait un outil robuste pour le prototypage.

## Voir aussi
- [Guide de l'utilisateur de JShell](https://docs.oracle.com/javase/9/jshell/introduction-jshell.htm)
- [Référence des outils de la plateforme Java, Édition Standard](https://docs.oracle.com/javase/9/tools/tools-and-command-reference.htm#JSWOR719)
- [API du compilateur Java](https://docs.oracle.com/javase/9/docs/api/javax/tools/JavaCompiler.html)
