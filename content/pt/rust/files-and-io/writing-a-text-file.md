---
title:                "Escrevendo um arquivo de texto"
aliases:
- /pt/rust/writing-a-text-file/
date:                  2024-02-03T19:29:18.734838-07:00
model:                 gpt-4-0125-preview
simple_title:         "Escrevendo um arquivo de texto"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/rust/writing-a-text-file.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## O que & Por quê?
Escrever um arquivo de texto em Rust envolve criar, escrever e, potencialmente, acrescentar dados a um arquivo no sistema de arquivos. Os programadores realizam essa operação para persistir dados, como logs de aplicativo, configuração ou conteúdo gerado pelo usuário, garantindo a durabilidade dos dados além do escopo da execução do programa.

## Como fazer:
A biblioteca padrão do Rust fornece ferramentas robustas para manipulação de arquivos, encapsuladas principalmente dentro dos módulos `std::fs` e `std::io`. Aqui está um exemplo básico para criar e escrever em um arquivo de texto:

```rust
use std::fs::File;
use std::io::prelude::*;

fn main() -> std::io::Result<()> {
    let mut file = File::create("hello.txt")?;
    file.write_all(b"Hello, world!")?;
    Ok(())
}
```

Depois de executar esse código, você encontrará um arquivo chamado `hello.txt` com o conteúdo "Hello, world!".

Para cenários mais complexos, como acrescentar a um arquivo ou lidar com dados maiores de forma eficiente, o Rust oferece funcionalidades adicionais. Veja como acrescentar texto a um arquivo existente:

```rust
use std::fs::OpenOptions;
use std::io::prelude::*;

fn main() -> std::io::Result<()> {
    let mut file = OpenOptions::new()
        .write(true)
        .append(true)
        .open("hello.txt")?;
        
    file.write_all(b" Adding more text.")?;
    Ok(())
}
```

Ao executar isso, será adicionado " Adding more text." ao final do `hello.txt`.

Em alguns casos, o uso de bibliotecas de terceiros pode simplificar as operações de arquivo. A crate `serde`, combinada com `serde_json`, por exemplo, permite serializar e desserializar estruturas de dados para e a partir do formato JSON, oferecendo uma abordagem de alto nível para escrever arquivos:

```rust
use serde::{Serialize, Deserialize};
use serde_json;
use std::fs::File;

#[derive(Serialize, Deserialize)]
struct User {
    id: u32,
    name: String,
}

fn main() -> std::io::Result<()> {
    let user = User { id: 1, name: "Jane Doe".into() };
    let file = File::create("user.json")?;
    serde_json::to_writer(file, &user)?;
    Ok(())
}
```

Após executar o código acima, `user.json` conterá uma representação em JSON da struct `User`. Note que usar `serde` e `serde_json` requer a adição dessas crates ao seu `Cargo.toml`.

Escrever arquivos de texto em Rust, seja através da biblioteca padrão ou com a ajuda de crates externas, é uma maneira direta, mas poderosa, de gerenciar a persistência de dados em suas aplicações.
