---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:34:06.891507-07:00
description: "Escrever para o erro padr\xE3o (stderr) no PowerShell envolve enviar\
  \ mensagens de erro ou diagn\xF3sticos diretamente para o stream stderr, distinto\
  \ do stream\u2026"
lastmod: '2024-03-13T22:44:46.813153-06:00'
model: gpt-4-0125-preview
summary: "Escrever para o erro padr\xE3o (stderr) no PowerShell envolve enviar mensagens\
  \ de erro ou diagn\xF3sticos diretamente para o stream stderr, distinto do stream\
  \ de sa\xEDda padr\xE3o (stdout)."
title: "Escrevendo para o erro padr\xE3o"
weight: 25
---

## Como Fazer:
O PowerShell simplifica o processo de escrever para stderr através do uso do cmdlet `Write-Error` ou direcionando a saída para o método `$host.ui.WriteErrorLine()`. No entanto, para a redireção direta de stderr, você pode preferir usar métodos .NET ou a redireção de descritor de arquivo oferecida pelo próprio PowerShell.

**Exemplo 1:** Usando `Write-Error` para escrever uma mensagem de erro para stderr.

```powershell
Write-Error "Esta é uma mensagem de erro."
```

Saída para stderr:
```
Write-Error: Esta é uma mensagem de erro.
```

**Exemplo 2:** Usando `$host.ui.WriteErrorLine()` para escrita direta em stderr.

```powershell
$host.ui.WriteErrorLine("Escrita direta em stderr.")
```

Saída para stderr:
```
Escrita direta em stderr.
```

**Exemplo 3:** Usando métodos .NET para escrever em stderr.

```powershell
[Console]::Error.WriteLine("Usando método .NET para stderr")
```

Saída deste método:
```
Usando método .NET para stderr
```

**Exemplo 4:** Redirecionando a saída de erro usando o descritor de arquivo `2>`.

Descritores de arquivos no PowerShell podem redirecionar diferentes streams. Para stderr, o descritor de arquivo é `2`. Aqui está um exemplo de redirecionamento de stderr para um arquivo chamado `error.log` enquanto executa um comando que gera um erro.

```powershell
Get-Item NonExistentFile.txt 2> error.log
```

Este exemplo não produz saída no console, mas gera um arquivo `error.log` no diretório atual contendo a mensagem de erro ao tentar acessar um arquivo que não existe.

Concluindo, o PowerShell oferece múltiplos métodos para escrever e gerenciar efetivamente a saída de erro, permitindo estratégias sofisticadas de tratamento de erros e registro de logs em scripts e aplicações.
