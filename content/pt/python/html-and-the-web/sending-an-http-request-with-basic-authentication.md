---
date: 2024-01-20 18:02:18.871370-07:00
description: "Enviar uma requisi\xE7\xE3o HTTP com autentica\xE7\xE3o b\xE1sica \xE9\
  \ o processo de acessar recursos protegidos em um servidor web, usando um nome de\
  \ usu\xE1rio e senha\u2026"
lastmod: '2024-03-13T22:44:46.153495-06:00'
model: gpt-4-1106-preview
summary: "Enviar uma requisi\xE7\xE3o HTTP com autentica\xE7\xE3o b\xE1sica \xE9 o\
  \ processo de acessar recursos protegidos em um servidor web, usando um nome de\
  \ usu\xE1rio e senha codificados em base64."
title: "Enviando uma requisi\xE7\xE3o HTTP com autentica\xE7\xE3o b\xE1sica"
weight: 45
---

## Como Fazer:
```Python
import requests
from requests.auth import HTTPBasicAuth

url = "http://algumsite.com/api/recurso"
username = "seu_usuario"
password = "sua_senha"

# Enviar a requisição com autenticação básica
response = requests.get(url, auth=HTTPBasicAuth(username, password))

print(response.status_code)
print(response.json())

# Muitas vezes você pode simplificar usando apenas (username, password):
response_simples = requests.get(url, auth=(username, password))

print(response_simples.status_code)
print(response_simples.json())
```
Saída esperada:
```
200
{"dados": "valor dos dados"}
200
{"dados": "valor dos dados"}
```

## Aprofundando:
A autenticação básica HTTP é um método antigo, mas ainda em uso devido à sua simplicidade. No passado, era a forma principal de autenticar, mas agora muitos consideram pouco segura porque as credenciais podem ser facilmente interceptadas se não usadas com HTTPS. Alternativas incluem autenticação Digest, OAuth e tokens de acesso.

A codificação Base64 não é uma tática de criptografia, o que significa que, embora obscureça suas credenciais, não as protege de olhares curiosos. Sempre use HTTPS quando enviar informações sensíveis.

Implementar corretamente a autenticação pode ser a diferença entre um sistema seguro e um convite aberto a vulnerabilidades. Ao desenvolver aplicações que se comunicam com APIs que necessitam de autenticação, garanta que você está seguindo as melhores práticas de segurança e dando atenção especial ao gerenciamento das credenciais.

## Veja Também:
- Documentação oficial do Requests sobre autenticação: https://docs.python-requests.org/en/latest/user/authentication/#basic-authentication
- RFC 7617, 'The 'Basic' HTTP Authentication Scheme': https://tools.ietf.org/html/rfc7617
- Mais sobre segurança com autenticação básica HTTP: https://www.owasp.org/index.php/Basic_Authentication
