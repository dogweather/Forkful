---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:09:08.332707-07:00
description: "Enviar uma requisi\xE7\xE3o HTTP com autentica\xE7\xE3o b\xE1sica em\
  \ Go envolve adicionar um cabe\xE7alho de autoriza\xE7\xE3o \xE0 sua requisi\xE7\
  \xE3o, que inclui um nome de usu\xE1rio e\u2026"
lastmod: '2024-03-13T22:44:46.060340-06:00'
model: gpt-4-0125-preview
summary: "Enviar uma requisi\xE7\xE3o HTTP com autentica\xE7\xE3o b\xE1sica em Go\
  \ envolve adicionar um cabe\xE7alho de autoriza\xE7\xE3o \xE0 sua requisi\xE7\xE3\
  o, que inclui um nome de usu\xE1rio e senha na forma de uma string codificada em\
  \ Base64."
title: "Enviando uma requisi\xE7\xE3o HTTP com autentica\xE7\xE3o b\xE1sica"
weight: 45
---

## Como fazer:
Para fazer uma requisição HTTP com autenticação básica em Go, você precisa preparar os cabeçalhos de sua requisição para incluir o campo `Authorization`, preenchido com suas credenciais no formato correto. Abaixo está um exemplo que demonstra como realizar uma solicitação GET para um endpoint de API que requer autenticação básica:

```go
package main

import (
	"fmt"
	"net/http"
	"encoding/base64"
)

func main() {
	client := &http.Client{}
	req, err := http.NewRequest("GET", "http://example.com/api/data", nil)
	if err != nil {
		panic(err)
	}

	username := "yourUsername"
	password := "yourPassword"
    // Codificar credenciais
	auth := base64.StdEncoding.EncodeToString([]byte(username + ":" + password))
    // Configurar cabeçalho de Autorização
	req.Header.Add("Authorization", "Basic " + auth)

	resp, err := client.Do(req)
	if err != nil {
		panic(err)
	}
	defer resp.Body.Close()

	fmt.Println("Status da resposta:", resp.Status)
}
```

Executar este código enviará uma solicitação GET para a URL especificada com o cabeçalho de Autorização necessário. A saída será algo assim, dependendo do seu endpoint e serviço:

```
Status da resposta: 200 OK
```

## Aprofundamento
A Autenticação Básica em requisições HTTP é um método amplamente suportado para aplicar controles de acesso a recursos da web. Ele simplesmente envia um nome de usuário e senha com cada requisição, tornando-o fácil de implementar mas não o método mais seguro disponível. Um grande inconveniente é que, a menos que usado em conjunto com SSL/TLS, as credenciais são enviadas em texto claro (já que Base64 é facilmente decodificado). Isso pode potencialmente expor informações sensíveis a ataques man-in-the-middle.

Em Go, enviar essas requisições envolve manipular diretamente o cabeçalho `Authorization`. Enquanto a biblioteca padrão de Go (`net/http`) fornece primitivas poderosas para lidar com comunicações HTTP(s), ela é relativamente de baixo nível, exigindo que os desenvolvedores lidem manualmente com vários aspectos do manuseio de requisições/respostas HTTP. Isso dá aos programadores muita flexibilidade, mas também significa que deve-se prestar mais atenção às implicações de segurança, codificação, e gerenciamento correto de cabeçalhos.

Para aplicações que requerem maior segurança, sistemas de autenticação mais avançados, como OAuth2 ou JWT (JSON Web Tokens), devem ser considerados. Essas abordagens fornecem funcionalidades de segurança mais robustas e são amplamente suportadas em APIs e serviços modernos. O ecossistema em expansão de Go inclui inúmeras bibliotecas e ferramentas (como `golang.org/x/oauth2`, entre outras) para facilitar esses métodos de autenticação mais seguros, tornando mais fácil para os desenvolvedores implementar mecanismos de autorização seguros, eficazes e modernos em suas aplicações.
