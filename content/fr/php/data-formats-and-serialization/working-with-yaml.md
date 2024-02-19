---
aliases:
- /fr/php/working-with-yaml/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:26:17.072015-07:00
description: "YAML, qui signifie \"YAML Ain't Markup Language\" (YAML n'est pas un\
  \ langage de balisage), est un format de s\xE9rialisation de donn\xE9es lisible\
  \ par l'homme\u2026"
lastmod: 2024-02-18 23:09:08.945147
model: gpt-4-0125-preview
summary: "YAML, qui signifie \"YAML Ain't Markup Language\" (YAML n'est pas un langage\
  \ de balisage), est un format de s\xE9rialisation de donn\xE9es lisible par l'homme\u2026"
title: Travailler avec YAML
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?

YAML, qui signifie "YAML Ain't Markup Language" (YAML n'est pas un langage de balisage), est un format de sérialisation de données lisible par l'homme couramment utilisé pour les fichiers de configuration. Les programmeurs choisissent d'utiliser YAML en raison de sa simplicité et de sa lisibilité, ce qui en fait un excellent choix pour stocker les paramètres, les configurations et même les structures de données complexes de manière facilement gérable.

## Comment faire :

PHP, dans ses itérations actuelles, ne supporte pas l'analyse de YAML comme partie de sa bibliothèque standard. La manière la plus directe de travailler avec YAML en PHP est d'utiliser le composant YAML de Symfony ou l'extension PECL `yaml`.

### Utiliser le composant YAML de Symfony

Tout d'abord, installez le composant YAML de Symfony via Composer :

```bash
composer require symfony/yaml
```

Ensuite, vous pouvez analyser et décharger le contenu YAML comme suit :

```php
<?php
require_once __DIR__.'/vendor/autoload.php';

use Symfony\Component\Yaml\Yaml;

// Analyse de YAML
$yamlString = <<<YAML
greet: Bonjour, le monde !
framework:
  name: Symfony
  language: PHP
YAML;

$array = Yaml::parse($yamlString);
print_r($array);

// Créer du YAML à partir d'un tableau
$array = [
    'greet' => 'Bonjour, YAML !',
    'framework' => [
        'name' => 'Symfony',
        'language' => 'PHP',
    ],
];

$yaml = Yaml::dump($array);
echo $yaml;
```

Exemple de sortie lors de l'analyse :

```
Array
(
    [greet] => Bonjour, le monde !
    [framework] => Array
        (
            [name] => Symfony
            [language] => PHP
        )

)
```

Exemple de sortie lors du déchargement :

```
greet: Bonjour, YAML !
framework:
    name: Symfony
    language: PHP
```

### Utiliser l'extension PECL `yaml`

Si vous préférez, ou si les exigences de votre projet le permettent, l'extension PECL peut être une autre manière efficace de travailler avec YAML. Tout d'abord, assurez-vous que l'extension est installée :

```bash
pecl install yaml
```

Puis, activez-la dans votre configuration `php.ini` :

```ini
extension=yaml.so
```

Voici comment analyser et émettre du YAML :

```php
<?php

// Analyse de YAML
$yamlString = <<<YAML
greet: Bonjour, le monde !
framework:
  name: Symfony
  language: PHP
YAML;

$array = yaml_parse($yamlString);
print_r($array);

// Créer du YAML à partir d'un tableau
$array = [
    'greet' => 'Bonjour, YAML !',
    'framework' => [
        'name' => 'Symfony',
        'language' => 'PHP',
    ],
];

$yaml = yaml_emit($array);
echo $yaml;
```

La sortie sera similaire à celle du composant Symfony, illustrant le rôle de YAML comme un pont entre le format lisible par l'homme et les structures de tableau PHP, facilitant ainsi la configuration et la manipulation des données.
