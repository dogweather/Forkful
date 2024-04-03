---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:59:16.752202-07:00
description: "Logging no desenvolvimento de software \xE9 o processo de registrar\
  \ informa\xE7\xF5es sobre a execu\xE7\xE3o de um programa, projetado para rastrear\
  \ seu comportamento e\u2026"
lastmod: '2024-03-13T22:44:46.067919-06:00'
model: gpt-4-0125-preview
summary: "Logging no desenvolvimento de software \xE9 o processo de registrar informa\xE7\
  \xF5es sobre a execu\xE7\xE3o de um programa, projetado para rastrear seu comportamento\
  \ e diagnosticar problemas."
title: Registro de Logs
weight: 17
---

## Como Fazer:
Em Go, o logging pode ser implementado usando o pacote da biblioteca padrão `log`. Este pacote fornece capacidades simples de logging, como escrever na saída padrão ou em arquivos. Vamos começar com um exemplo básico de logging para a saída padrão:

```go
package main

import (
	"log"
)

func main() {
	log.Println("Esta é uma entrada de log básica.")
}
```

Saída:
```
2009/11/10 23:00:00 Esta é uma entrada de log básica.
```

O carimbo de data/hora no início da entrada de log é adicionado automaticamente pelo pacote `log`. A seguir, vamos explorar como fazer log para um arquivo em vez da saída padrão:

```go
package main

import (
	"log"
	"os"
)

func main() {
	file, err := os.OpenFile("app.log", os.O_CREATE|os.O_APPEND|os.O_WRONLY, 0666)
	if err != nil {
		log.Fatal(err)
	}
	defer file.Close()

	log.SetOutput(file)
	log.Println("Esta entrada de log vai para um arquivo.")
}
```

Agora, vamos implementar um caso de uso mais avançado: personalizando o formato de logging. Go permite que você crie um logger personalizado com `log.New()`:

```go
package main

import (
	"log"
	"os"
)

func main() {
	logger := log.New(os.Stdout, "LOG PERSONALIZADO: ", log.Ldate|log.Ltime|log.Lshortfile)
	logger.Println("Esta é uma mensagem de log personalizada.")
}
```

Saída:
```
LOG PERSONALIZADO: 2009/11/10 23:00:00 main.go:11: Esta é uma mensagem de log personalizada.
```

Este exemplo prefixa cada mensagem de log com "LOG PERSONALIZADO: " e inclui a data, a hora e a localização do arquivo fonte.

## Aprofundamento
O pacote `log` da biblioteca padrão do Go é direto e suficiente para muitas aplicações, mas carece de algumas características mais sofisticadas encontradas em bibliotecas de logging de terceiros, como logging estruturado, rotação de logs e logging baseado em níveis. Pacotes como `zap` e `logrus` oferecem essas características avançadas e são bem-regardados na comunidade Go por seu desempenho e flexibilidade.

Por exemplo, o logging estruturado permite que você registre dados em um formato estruturado (como JSON), o que é especialmente útil para aplicações modernas baseadas na nuvem, onde os logs podem ser analisados por várias ferramentas ou serviços. `zap`, em particular, é conhecido por seu alto desempenho e baixa sobrecarga de alocação, tornando-o adequado para aplicações onde velocidade e eficiência são críticas.

Historicamente, o logging em Go evoluiu significativamente desde a criação da linguagem. As primeiras versões do Go forneciam as capacidades básicas de logging que vemos no pacote `log`. No entanto, à medida que a linguagem cresceu em popularidade e a complexidade das aplicações escritas em Go aumentou, a comunidade começou a desenvolver bibliotecas de logging mais sofisticadas para atender às suas necessidades. Hoje, enquanto o pacote `log` padrão permanece uma opção viável para aplicações simples, muitos desenvolvedores recorrem a essas soluções de terceiros para requisitos de logging mais complexos.
