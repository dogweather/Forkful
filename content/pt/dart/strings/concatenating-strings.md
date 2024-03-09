---
title:                "Concatenando strings"
date:                  2024-03-08T21:53:31.462000-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## O que & Por quê?
Concatenar strings na programação envolve combinar duas ou mais strings em uma. Os programadores fazem isso para manipular dados de texto com facilidade, construir mensagens ou montar partes de uma interface de usuário de forma dinâmica.

## Como fazer:
O Dart oferece várias maneiras simples de concatenar strings. Abaixo estão os métodos mais comuns:

### Usando o Operador `+`
O operador `+` é a maneira mais intuitiva de juntar strings.
```dart
String cumprimento = 'Olá, ' + 'Mundo!';
print(cumprimento); // Saída: Olá, Mundo!
```

### Usando o Método `concat()`
Embora o Dart não tenha um método `concat()` semelhante a outras linguagens, alcançar o mesmo pode ser feito usando `+` ou os métodos a seguir.

### Usando Interpolação de Strings
A interpolação de strings permite que variáveis sejam embutidas diretamente dentro de uma string. É eficiente para combinar strings e expressões.
```dart
String usuario = 'Jane';
String mensagem = 'Bem-vindo(a), $usuario!';
print(mensagem); // Saída: Bem-vindo(a), Jane!
```

### Usando o Método `join()`
O método `join()` é útil quando você tem uma lista de strings que deseja concatenar.
```dart
var palavras = ['Olá', 'do', 'Dart'];
String frase = palavras.join(' '); // Juntar com um separador de espaço.
print(frase); // Saída: Olá do Dart
```

### Usando StringBuffer
`StringBuffer` é eficiente para múltiplas concatenações, especialmente em loops.
```dart
var palavras = ['Dart', 'é', 'divertido'];
StringBuffer buffer = StringBuffer();
for (String palavra in palavras) {
  buffer.write(palavra); // Anexar cada palavra ao buffer.
  buffer.write(' '); // Opcionalmente adicionar um espaço.
}
String frase = buffer.toString().trim(); // Converter para string e remover espaço final.
print(frase); // Saída: Dart é divertido
```

### Bibliotecas de Terceiros
Embora a biblioteca padrão do Dart seja geralmente suficiente para tarefas de concatenação de strings, bibliotecas de terceiros como `quiver` oferecem utilitários que podem complementar a funcionalidade integrada do Dart. Por exemplo, as funções `concat()` ou `merge()` do `quiver` podem ser exploradas para cenários avançados. No entanto, apegue-se às robustas opções integradas do Dart, a menos que você tenha uma necessidade específica que elas não cobrem.
