---
date: 2024-01-20 18:02:19.860910-07:00
description: "Enviar uma requisi\xE7\xE3o HTTP com autentica\xE7\xE3o b\xE1sica significa\
  \ que voc\xEA fornece um nome de usu\xE1rio e senha para acessar um recurso protegido\
  \ online.\u2026"
lastmod: '2024-03-13T22:44:46.667075-06:00'
model: gpt-4-1106-preview
summary: "Enviar uma requisi\xE7\xE3o HTTP com autentica\xE7\xE3o b\xE1sica significa\
  \ que voc\xEA fornece um nome de usu\xE1rio e senha para acessar um recurso protegido\
  \ online."
title: "Enviando uma requisi\xE7\xE3o HTTP com autentica\xE7\xE3o b\xE1sica"
weight: 45
---

## Como fazer:
```PHP
<?php
$url = 'https://algumservidor.com/api/recurso'; // Substitua pela URL do recurso
$usuario = 'seunome'; // Substitua pelo seu nome de usuário
$senha = 'suasenha'; // Substitua pela sua senha

$contexto = stream_context_create([
    'http' => [
        'header' => 'Authorization: Basic ' . base64_encode("$usuario:$senha")
    ]
]);

$resposta = file_get_contents($url, false, $contexto);

if ($resposta === FALSE) {
    // Lide com o erro
    echo "Houve um erro na requisição.";
} else {
    echo $resposta; // Saída da resposta
}
?>
```

## Aprofundando:
A autenticação básica é um método antigo, mas ainda usado, de enviar credenciais de acesso via HTTP de forma não muito segura, pois as credenciais são enviadas em texto simples codificado em Base64. Alternativas mais seguras hoje em dia incluem tokens de acesso, como OAuth. Para detalhes de implementação, ao usar a autenticação básica, é essencial que a comunicação ocorra sobre HTTPS para prevenir a exposição das credenciais. Lembre-se também de proteger seus scripts para que informações de autenticação não se tornem acessíveis.

## Veja Também:
- Documentação do PHP sobre contextos de fluxo: [PHP: Contextos de Fluxo](https://www.php.net/manual/pt_BR/context.php)
- Guia sobre autenticação básica pelo MDN: [MDN Web Docs - HTTP authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication)
- Informações sobre segurança em autenticação via HTTP: [OWASP - Authentication Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html)
