---
title:                "Trabalhando com CSV"
date:                  2024-03-08T21:57:46.330008-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## O Que & Por Quê?

Trabalhar com arquivos CSV (Valores Separados por Vírgula) envolve analisar e gerar arquivos de texto onde cada linha contém valores separados por vírgulas. Os programadores fazem isso para possibilitar a troca de dados entre diferentes aplicativos ou para facilitar o armazenamento de dados em um formato leve e legível por humanos.

## Como Fazer:

Para manipular arquivos CSV em Dart, você geralmente processa o texto manualmente ou usa bibliotecas de terceiros para simplificar a tarefa. Aqui, vamos olhar para ambas as abordagens.

### Analisando CSV Manualmente

Se suas necessidades são simples, você pode optar por analisar uma string CSV manualmente. Isso pode ser alcançado usando as funções de manipulação de string do próprio Dart:

```dart
void main() {
  // Dados CSV de exemplo
  String csvData = "Nome,Idade,Email\nJohn Doe,30,john@example.com\nJane Smith,25,jane@example.com";
  
  // Dividindo os dados CSV em linhas
  List<String> linhas = csvData.split('\n');
  
  // Analisando cada linha
  List<Map<String, String>> dados = [];
  List<String> cabecalhos = linhas.first.split(',');
  
  for (var i = 1; i < linhas.length; i++) {
    List<String> linha = linhas[i].split(',');
    Map<String, String> registro = {};
    for (var j = 0; j < cabecalhos.length; j++) {
      registro[cabecalhos[j]] = linha[j];
    }
    dados.add(registro);
  }
  
  // Exibindo os dados analisados
  print(dados);
}

// Saída de exemplo:
// [{Nome: John Doe, Idade: 30, Email: john@example.com}, {Nome: Jane Smith, Idade: 25, Email: jane@example.com}]
```

### Usando uma Biblioteca de Terceiros: `csv`

Para cenários mais complexos ou para simplificar seu código, você pode usar uma biblioteca de terceiros popular como `csv`. Primeiro, adicione-a ao seu projeto incluindo `csv: ^5.0.0` (ou a versão mais recente) no seu arquivo `pubspec.yaml` sob `dependencies`. Em seguida, use-a da seguinte maneira:

```dart
import 'package:csv/csv.dart';

void main() {
  String csvData = "Nome,Idade,Email\nJohn Doe,30,john@example.com\nJane Smith,25,jane@example.com";
  
  // Use o CsvToListConverter para analisar os dados CSV
  List<List<dynamic>> dadosLista = const CsvToListConverter().convert(csvData);
  
  // O primeiro item da lista contém os cabeçalhos
  List<String> cabecalhos = dadosLista.first.map((item) => item.toString()).toList();
  
  // Removendo a linha do cabeçalho antes de processar mais
  dadosLista.removeAt(0);
  
  // Converter para List<Map<String, dynamic>> para um formato mais estruturado
  List<Map<String, dynamic>> dadosMapeados = dadosLista.map((lista) {
    Map<String, dynamic> mapa = {};
    for (int i = 0; i < cabecalhos.length; i++) {
      mapa[cabecalhos[i]] = lista[i];
    }
    return mapa;
  }).toList();
  
  // Exibindo os dados mapeados
  print(dadosMapeados);
}

// Saída de exemplo:
// [{Nome: John Doe, Idade: 30, Email: john@example.com}, {Nome: Jane Smith, Idade: 25, Email: jane@example.com}]
```

Ambos os métodos demonstram como trabalhar com dados CSV: o primeiro manualmente, para fins de aprendizado ou quando lidando com estruturas CSV muito simples; o segundo, aproveitando uma biblioteca poderosa que simplifica a análise e pode lidar com várias complexidades do formato CSV.
