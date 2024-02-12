---
title:                "Organisation du code en fonctions"
aliases:
- fr/java/organizing-code-into-functions.md
date:                  2024-01-26T01:10:30.156239-07:00
model:                 gpt-4-1106-preview
simple_title:         "Organisation du code en fonctions"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/java/organizing-code-into-functions.md"
---

{{< edit_this_page >}}

## Quoi et pourquoi ?
Organiser le code en fonctions signifie décomposer le monstre qu'est un programme en morceaux gérables, chacun effectuant une tâche distincte. Les programmeurs font cela pour rendre le code lisible, réutilisable et maintenable.

## Comment faire :
Voici un exemple classique — une fonction pour calculer le factoriel d'un nombre.

```java
public class MathUtils {

    public static void main(String[] args) {
        int nombre = 5;
        int resultat = factoriel(nombre);
        System.out.println("Le factoriel de " + nombre + " est : " + resultat);
    }
    
    public static int factoriel(int n) {
        if (n <= 1) {
            return 1;
        }
        return n * factoriel(n - 1);
    }
}
```

Le résultat serait :
```
Le factoriel de 5 est : 120
```

## Plongée en profondeur
Avant que les fonctions ne soient une chose, le code était entassé dans des blocs monolithiques, rendant le débogage comme chercher une aiguille dans une botte de foin. Aujourd'hui, encapsuler la fonctionnalité en fonctions aide à isoler rapidement les problèmes. Les alternatives incluent les expressions lambda en Java ou les méthodes en programmation orientée objet, qui servent toutes deux à des fins similaires. Lorsque vous écrivez une fonction, souvenez-vous : (1) Chaque fonction devrait avoir une seule responsabilité et (2) le nom de la fonction devrait clairement décrire son but.

## Voir aussi
Pour en savoir plus sur l'organisation du code :
- Clean Code de Robert C. Martin
- Refactoring : Improving the Design of Existing Code de Martin Fowler
- [Documentation Oracle Java sur la définition des méthodes](https://docs.oracle.com/javase/tutorial/java/javaOO/methods.html)
