---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:08:37.614608-07:00
description: "Dans le d\xE9veloppement de logiciels, il est souvent n\xE9cessaire\
  \ de v\xE9rifier si un r\xE9pertoire existe pour \xE9viter les erreurs lors de la\
  \ tentative d'acc\xE8s, de\u2026"
lastmod: '2024-03-13T22:44:57.498341-06:00'
model: gpt-4-0125-preview
summary: "Dans le d\xE9veloppement de logiciels, il est souvent n\xE9cessaire de v\xE9\
  rifier si un r\xE9pertoire existe pour \xE9viter les erreurs lors de la tentative\
  \ d'acc\xE8s, de lecture ou d'\xE9criture de fichiers."
title: "V\xE9rifier si un r\xE9pertoire existe"
weight: 20
---

## Comment faire :
La bibliothèque standard de Rust (`std`) inclut des fonctionnalités pour vérifier l'existence d'un répertoire à travers les modules `std::path::Path` et `std::fs`. Voici un exemple simple utilisant l'approche standard de Rust :

```rust
use std::path::Path;

fn main() {
    let path = Path::new("/chemin/vers/repertoire");
    if path.exists() && path.is_dir() {
        println!("Le répertoire existe.");
    } else {
        println!("Le répertoire n'existe pas.");
    }
}
```

Sortie d'échantillon, en supposant que le répertoire existe :
```
Le répertoire existe.
```

Pour des scénarios plus complexes ou des fonctionnalités améliorées (comme les opérations de système de fichiers asynchrones), vous pourriez envisager d'utiliser une bibliothèque tierce telle que `tokio` avec son module `fs` asynchrone, surtout si vous travaillez dans un runtime asynchrone. Voici comment vous pourriez réaliser la même chose avec `tokio` :

D'abord, ajoutez `tokio` à votre `Cargo.toml` :

```toml
[dependencies]
tokio = { version = "1.0", features = ["full"] }
```

Ensuite, utilisez `tokio::fs` pour vérifier de manière asynchrone si un répertoire existe :

```rust
use tokio::fs;

#[tokio::main]
async fn main() {
    let path = "/chemin/vers/repertoire";
    match fs::metadata(path).await {
        Ok(metadata) => {
            if metadata.is_dir() {
                println!("Le répertoire existe.");
            } else {
                println!("Le chemin existe mais ce n'est pas un répertoire.");
            }
        },
        Err(_) => println!("Le répertoire n'existe pas."),
    }
}
```

Sortie d'échantillon, en supposant que le répertoire n'existe pas :
```
Le répertoire n'existe pas.
```

Ces exemples soulignent comment Rust et son écosystème offrent à la fois des approches synchrones et asynchrones pour vérifier l'existence de répertoires, répondant à une large gamme de besoins en développement logiciel.
