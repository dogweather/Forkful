---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:33:38.923033-07:00
description: "\xC9crire sur la sortie d'erreur standard (stderr) consiste \xE0 afficher\
  \ des messages d'erreur et des diagnostics sur la console ou le terminal. Les\u2026"
lastmod: '2024-03-13T22:44:57.660169-06:00'
model: gpt-4-0125-preview
summary: "\xC9crire sur la sortie d'erreur standard (stderr) consiste \xE0 afficher\
  \ des messages d'erreur et des diagnostics sur la console ou le terminal."
title: "\xC9crire sur l'erreur standard"
weight: 25
---

## Comment faire :


### Sortie stderr basique en Java
Java fournit une manière simple d'écrire sur stderr en utilisant `System.err.print()` ou `System.err.println()`. Voici comment vous le faites :

```java
public class StdErrExample {
    public static void main(String[] args) {
        try {
            int division = 10 / 0;
        } catch (ArithmeticException e) {
            System.err.println("Erreur : Impossible de diviser par zéro.");
        }
    }
}
```

Sortie d'exemple :

```
Erreur : Impossible de diviser par zéro.
```

Cela imprimera directement le message d'erreur sur le flux d'erreur standard.

### Utiliser un système de log pour une gestion d'erreurs avancée
Pour des applications nécessitant une gestion d'erreurs et des logs plus sophistiqués, l'utilisation d'une bibliothèque de journalisation comme SLF4J avec Logback ou Log4J2 est courante. Cela permet une plus grande flexibilité dans la gestion de la sortie d'erreurs, incluant la redirection de fichiers, le filtrage et la mise en forme.

#### Exemple avec Logback
D'abord, ajoutez la dépendance pour Logback à votre fichier `pom.xml` (Maven) ou `build.gradle` (Gradle). Pour Maven :

```xml
<dependency>
    <groupId>ch.qos.logback</groupId>
    <artifactId>logback-classic</artifactId>
    <version>1.2.3</version>
</dependency>
```

Ensuite, vous pouvez utiliser le code suivant pour enregistrer les erreurs :

```java
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class LoggerExample {
    private static final Logger logger = LoggerFactory.getLogger(LoggerExample.class);
    
    public static void main(String[] args) {
        try {
            int result = 10 / 0;
        } catch (ArithmeticException e) {
            logger.error("Erreur : Impossible de diviser par zéro.", e);
        }
    }
}
```

Cela produira le message d'erreur avec une trace de pile sur la console ou dans un fichier, selon la configuration de Logback.

Utiliser des cadres de journalisation comme Logback offre plus de contrôle sur la gestion des erreurs, rendant plus facile la gestion des applications et des systèmes de grande envergure.
