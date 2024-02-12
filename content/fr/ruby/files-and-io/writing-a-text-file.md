---
title:                "Rédiger un fichier texte"
aliases:
- /fr/ruby/writing-a-text-file/
date:                  2024-02-03T19:29:04.067481-07:00
model:                 gpt-4-0125-preview
simple_title:         "Rédiger un fichier texte"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/ruby/writing-a-text-file.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?
Écrire dans un fichier texte en Ruby est une opération fondamentale qui vous permet de stocker des sorties et des données de manière persistante, permettant ainsi aux données d'être consultées ou modifiées ultérieurement. Les programmeurs effectuent souvent cette tâche pour des raisons telles que la journalisation, la sauvegarde de configurations ou l'exportation de données dans un format lisible par l'homme.

## Comment faire :
Ruby rend les opérations sur les fichiers simples. Pour écrire dans un fichier, vous pouvez utiliser la classe `File` intégrée à Ruby. L'exemple suivant démontre comment ouvrir un fichier pour l'écriture (mode `"w"`) et pour l'append (mode `"a"`), puis écrire une chaîne dans celui-ci et s'assurer que le fichier est fermé ensuite :

```ruby
# Écrire un nouveau contenu dans un fichier, en écrasant le contenu existant
File.open("example.txt", "w") do |file|
  file.puts "Bonjour, Ruby!"
end

# Ajouter du contenu à la fin d'un fichier
File.open("example.txt", "a") do |file|
  file.puts "Ajout d'une autre ligne."
end
```
Après avoir exécuté les deux extraits, le contenu de `example.txt` sera :
```
Bonjour, Ruby!
Ajout d'une autre ligne.
```

### Utiliser une bibliothèque tierce : FileUtils
Pour des opérations sur les fichiers plus complexes, la bibliothèque standard de Ruby `FileUtils` peut être très utile, bien que pour l'écriture de fichiers basique, les méthodes standard de `File` soient suffisantes. Cependant, si vous souhaitez copier, déplacer, supprimer ou effectuer d'autres opérations sur le système de fichiers en conjonction avec l'écriture de fichiers, `FileUtils` vaut la peine d'être explorée.

Un exemple d'utilisation de `FileUtils` pour créer un répertoire puis écrire dans un fichier dans ce répertoire :
```ruby
require 'fileutils'

FileUtils.mkdir_p 'logs'
File.open("logs/aujourd'hui.log", "w") do |file|
  file.puts "Entrée du journal : #{Time.now}"
end
```

Cela démontre la création d'un nouveau répertoire `logs` s'il n'existe pas déjà, et l'écriture dans un nouveau fichier `aujourd'hui.log` à l'intérieur, montrant à la fois la manipulation de répertoires et de fichiers sans écrire directement avec FileUtils, mais en utilisant sa capacité de gestion de répertoires.
