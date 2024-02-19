---
aliases:
- /pt/rust/removing-quotes-from-a-string/
date: 2024-01-26 03:42:07.682803-07:00
description: "Remover aspas de uma string no Rust \xE9 sobre eliminar caracteres de\
  \ aspas extras desnecess\xE1rios que podem estar envolvendo seus dados de texto.\u2026"
lastmod: 2024-02-18 23:08:57.915700
model: gpt-4-0125-preview
summary: "Remover aspas de uma string no Rust \xE9 sobre eliminar caracteres de aspas\
  \ extras desnecess\xE1rios que podem estar envolvendo seus dados de texto.\u2026"
title: Removendo aspas de uma string
---

{{< edit_this_page >}}

## O Que e Por quê?

Remover aspas de uma string no Rust é sobre eliminar caracteres de aspas extras desnecessários que podem estar envolvendo seus dados de texto. Programadores fazem isso quando precisam limpar ou normalizar strings, talvez após analisar dados de um arquivo, ou ao prepará-los para outro formato onde as aspas possam ser problemáticas ou redundantes.

## Como fazer:

```Rust
fn remove_quotes(s: &str) -> String {
    s.trim_matches(|c| c == '\"' || c == '\'').to_string()
}

fn main() {
    let quoted_str = "\"Olá, Rustaceanos!\"";
    let cleaned_str = remove_quotes(quoted_str);
    println!("{}", cleaned_str);
    // Saída: Olá, Rustaceanos!
}
```

Às vezes você tem uma string com aspas misturadas, assim:

```Rust
fn main() {
    let mixed_quoted = "'Rust diz: \"Olá, Mundo!\"'";
    let cleaned_str = remove_quotes(mixed_quoted);
    println!("{}", cleaned_str);
    // Saída: Rust diz: "Olá, Mundo!"
}
```
Aqui, apenas as aspas simples mais externas são removidas.

## Aprofundamento

Ao remover aspas de uma string, você pode se perguntar por que não é apenas um simples `.replace("\"", "")`. No início, lidar com texto era menos padronizado, e diferentes sistemas tinham diferentes formas de armazenar e transmitir texto, muitas vezes com algum tipo de 'sequência de escape' para caracteres especiais. O método `trim_matches` do Rust é mais versátil, permitindo que você especifique múltiplos caracteres para aparar, e se deseja aparar do início (prefixo), do fim (sufixo) ou de ambos os lados da string.

Existem alternativas, claro. Regex é a potência para manipulação de strings, capaz de combinar padrões complexos, e seria excessivo apenas para remover aspas. Bibliotecas como `trim_in_place` poderiam oferecer um aparar no local sem a sobrecarga de criar um novo objeto `String`, o que poderia ser desejável para aplicações críticas de desempenho.

Por baixo dos panos, `trim_matches` na verdade itera pelos caracteres da string de ambos os extremos, verificando contra o padrão fornecido até encontrar um caractere que não corresponda. É eficiente para o que faz, mas esteja sempre ciente de que está trabalhando com valores escalares Unicode. Se sua string pode conter caracteres Unicode de múltiplos bytes, você não precisa se preocupar com ela quebrando-os.

## Veja Também

- Documentação do Rust sobre manipulação de strings: https://doc.rust-lang.org/book/ch08-02-strings.html
- A crate `regex` para padrões complexos: https://crates.io/crates/regex
- Rust por Exemplo para cenários práticos de codificação: https://doc.rust-lang.org/stable/rust-by-example/std/str.html
