---
title:                "Criando um arquivo temporário"
date:                  2024-01-20T17:39:31.781304-07:00
model:                 gpt-4-1106-preview
simple_title:         "Criando um arquivo temporário"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/arduino/creating-a-temporary-file.md"
---

{{< edit_this_page >}}

## O que é & Porquê?

Criar um arquivo temporário é o processo de gerar um ficheiro que só é necessário durante a execução de um programa ou tarefa. Programadores fazem isso para armazenar dados temporários que não precisam ser preservados após o término do programa.

## Como fazer:

No contexto do Arduino, criar um arquivo temporário geralmente envolve escrever em um cartão SD, pois o Arduino não tem um sistema de arquivos tradicional integrado. Aqui está um exemplo simples usando a biblioteca `SD`.

```Arduino
#include <SPI.h>
#include <SD.h>

File meuArquivoTemp;

void setup() {
  Serial.begin(9600);
  while (!Serial) {
    ; // espera a conexão serial
  }

  if (!SD.begin(4)) {
    Serial.println("Falha na inicialização do SD.");
    return;
  }
   
  // Cria um arquivo temporário com um nome aleatório
  String nomeArquivo = "temp" + String(random(1000, 9999)) + ".txt";
  meuArquivoTemp = SD.open(nomeArquivo, FILE_WRITE);
  
  if (meuArquivoTemp) {
    Serial.println("Arquivo temporário criado.");
    meuArquivoTemp.println("Isso é um teste!");
    meuArquivoTemp.close(); // Fecha o arquivo ao terminar
  } else {
    Serial.println("Erro ao criar o arquivo.");
  }
}

void loop() {
  // A lógica do programa vai aqui.
}
```

A saída deve ser algo como "Arquivo temporário criado." no Monitor Serial, e você terá um arquivo no cartão SD com conteúdo de teste.

## Mergulho Profundo

Na era do Arduino, criar arquivos temporários em cartões SD é uma conveniência para lidar com dados de forma não permanente. Históricamente, sistemas computacionais utilizam arquivos temporários para manipulação de dados em processos intermediários, ajudando a reduzir o uso de memória e permitindo a recuperação em casos de falhas. No contexto do Arduino, temos que trabalhar com armazenamentos externos como cartões SD ou similares, pois a placa em si tem capacidade limitada e não suporta um sistema de arquivos persistente.

Existem alternativas, como usar uma memória EEPROM do Arduino para guardar dados mais permanentemente (embora seja um espaço limitado), ou conectar o Arduino a um computador ou a uma rede e enviar os dados temporários para lá, evitando o uso do cartão SD.

Do ponto de vista da implementação, é crucial gerenciar bem o espaço limitado do cartão SD e garantir que os arquivos temporários sejam devidamente excluídos ou reescritos conforme a necessidade para evitar o preenchimento do cartão SD.

## Veja Também

- Documentação da biblioteca SD para Arduino: [arduino.cc/en/Reference/SD](https://www.arduino.cc/en/Reference/SD)
- Guia da memória EEPROM no Arduino: [arduino.cc/en/Reference/EEPROM](https://www.arduino.cc/en/Reference/EEPROM)
- Tutorial sobre a comunicação serial com Arduino: [arduino.cc/en/Serial/Read](https://www.arduino.cc/en/Serial/Read)
