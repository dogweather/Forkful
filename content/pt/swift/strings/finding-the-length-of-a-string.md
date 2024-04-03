---
date: 2024-01-20 17:48:25.782262-07:00
description: "Saber o comprimento de uma string \xE9 descobrir quantos caracteres\
  \ ela cont\xE9m. Programadores fazem isso para validar entradas, manipular textos\
  \ ou at\xE9 mesmo\u2026"
lastmod: '2024-03-13T22:44:46.912043-06:00'
model: gpt-4-1106-preview
summary: "Saber o comprimento de uma string \xE9 descobrir quantos caracteres ela\
  \ cont\xE9m."
title: Descobrindo o comprimento de uma string
weight: 7
---

## Como fazer:
```swift
let saudacao = "Olá, mundo!"
let comprimento = saudacao.count

print("O comprimento da string é \(comprimento)")
// Saída: O comprimento da string é 12
```

Para strings com caracteres especiais:

```swift
let emoji = "🇧🇷"
print("O comprimento do emoji é \(emoji.count)")
// Saída: O comprimento do emoji é 1
```

Lembre-se que Swift trata os Emojis como caracteres únicos, independentemente da sua complexidade.

## Mergulho Profundo
Em versões anteriores do Swift, você poderia ter usado `saudacao.characters.count`, mas isso foi simplificado. Hoje, `.count` faz o trabalho sem complicações. Há alternativas, como `NSString` do Objective-C, que contam os caracteres de maneira diferente, considerando detalhes de codificação UTF-16.

```swift
let texto = "Café"
let nsStringComprimento = (texto as NSString).length
print("NSString comprimento: \(nsStringComprimento)")
// Saída: NSString comprimento: 4
```

Note que o `NSString` conta o caractere "é" como dois caracteres (codificação UTF-16), enquanto `String` no Swift conta corretamente como um.

Importante: `.count` no Swift executa em tempo linear com o número de caracteres Unicode, porque ele percorre toda a string para fazer a contagem correta, considerando todos os grapheme clusters como um único caractere visível.

## Veja Também
- Documentação oficial da Apple para Strings em Swift: [Strings and Characters](https://docs.swift.org/swift-book/LanguageGuide/StringsAndCharacters.html)
- Unicode Consortium para entender mais sobre grapheme clusters e Unicode: [Unicode Standard](http://www.unicode.org/standard/standard.html)
