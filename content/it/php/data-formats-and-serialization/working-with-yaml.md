---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:26:19.632344-07:00
description: "YAML, acronimo di \"YAML Ain't Markup Language\", \xE8 un formato di\
  \ serializzazione dei dati leggibile dall'uomo comunemente usato per i file di\u2026"
lastmod: '2024-03-13T22:44:43.537025-06:00'
model: gpt-4-0125-preview
summary: "YAML, acronimo di \"YAML Ain't Markup Language\", \xE8 un formato di serializzazione\
  \ dei dati leggibile dall'uomo comunemente usato per i file di configurazione."
title: Lavorare con YAML
weight: 41
---

## Come fare:
PHP, nelle sue versioni attuali, non supporta l'analisi di YAML come parte della sua libreria standard. Il modo più diretto per lavorare con YAML in PHP è utilizzare il componente YAML di Symfony o l'estensione PECL `yaml`.

### Utilizzando il Componente YAML di Symfony
Prima di tutto, installa il componente YAML di Symfony tramite Composer:

```bash
composer require symfony/yaml
```

Poi, puoi analizzare e generare contenuti YAML come segue:

```php
<?php
require_once __DIR__.'/vendor/autoload.php';

use Symfony\Component\Yaml\Yaml;

// Analisi YAML
$yamlString = <<<YAML
greet: Ciao, Mondo!
framework:
  name: Symfony
  language: PHP
YAML;

$array = Yaml::parse($yamlString);
print_r($array);

// Creazione di YAML da un array
$array = [
    'greet' => 'Ciao, YAML!',
    'framework' => [
        'name' => 'Symfony',
        'language' => 'PHP',
    ],
];

$yaml = Yaml::dump($array);
echo $yaml;
```

Output di esempio durante l'analisi:

```
Array
(
    [greet] => Ciao, Mondo!
    [framework] => Array
        (
            [name] => Symfony
            [language] => PHP
        )

)
```

Output di esempio durante la generazione:

```
greet: Ciao, YAML!
framework:
    name: Symfony
    language: PHP
```

### Utilizzando l'Estensione PECL `yaml`
Se preferisci, o se i requisiti del tuo progetto lo consentono, l'estensione PECL può essere un altro modo efficiente per lavorare con YAML. Prima di tutto, assicurati che l'estensione sia installata:

```bash
pecl install yaml
```

Poi, abilitala nella tua configurazione `php.ini`:

```ini
extension=yaml.so
```

Ecco come analizzare ed emettere YAML:

```php
<?php

// Analisi YAML
$yamlString = <<<YAML
greet: Ciao, Mondo!
framework:
  name: Symfony
  language: PHP
YAML;

$array = yaml_parse($yamlString);
print_r($array);

// Creazione di YAML da un array
$array = [
    'greet' => 'Ciao, YAML!',
    'framework' => [
        'name' => 'Symfony',
        'language' => 'PHP',
    ],
];

$yaml = yaml_emit($array);
echo $yaml;
```

L'output sarà simile a quello del componente Symfony, illustrando il ruolo di YAML come ponte tra il formato leggibile dall'uomo e le strutture di array PHP, facilitando una configurazione e gestione dei dati più semplice.
