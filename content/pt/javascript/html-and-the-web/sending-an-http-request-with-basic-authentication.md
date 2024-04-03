---
date: 2024-01-20 18:02:10.606316-07:00
description: "Enviar um pedido HTTP com autentica\xE7\xE3o b\xE1sica significa incluir\
  \ credenciais de usu\xE1rio e senha codificados em base-64 no cabe\xE7alho do pedido.\u2026"
lastmod: '2024-03-13T22:44:46.962330-06:00'
model: gpt-4-1106-preview
summary: "Enviar um pedido HTTP com autentica\xE7\xE3o b\xE1sica significa incluir\
  \ credenciais de usu\xE1rio e senha codificados em base-64 no cabe\xE7alho do pedido."
title: "Enviando uma requisi\xE7\xE3o HTTP com autentica\xE7\xE3o b\xE1sica"
weight: 45
---

## Como Fazer:
```Javascript
// Utilizando o módulo 'axios' para fazer o pedido HTTP com autenticação básica.
const axios = require('axios');
const base64Credentials = Buffer.from('usuario:senha').toString('base64');

axios.get('https://algumsite.com/dados', {
  headers: {
    'Authorization': `Basic ${base64Credentials}`
  }
})
.then(response => {
  console.log('Dados recebidos:', response.data);
})
.catch(error => {
  console.error('Erro na requisição:', error);
});
```
Saída esperada (sample output):
```
Dados recebidos: { ... } // Dados retornados do servidor
```

## Mergulho Profundo
A autenticação básica é um protocolo simples de autenticação incluído nos padrões HTTP iniciados nos anos 90. Alternativas mais seguras, como OAuth e JWT (JSON Web Tokens), são recomendadas para novas aplicações devido a uma maior segurança. Na autenticação básica, usuário e senha são codificados, mas não criptografados, o que pode ser um risco de segurança se não utilizado com HTTPS. A implementação acima é direta em Node.js usando o axios, mas pode ser adaptada para outros ambientes Javascript.

## Veja Também
- MDN Web Docs sobre autenticação HTTP: https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication
- RFC 7617, "The 'Basic' HTTP Authentication Scheme": https://tools.ietf.org/html/rfc7617
- Comparação entre autenticação básica e OAuth: https://auth0.com/docs/authoriza/authenticate/http-authentication/basic-auth-vs-oauth
- Documentação do axios: https://axios-http.com/docs/intro
