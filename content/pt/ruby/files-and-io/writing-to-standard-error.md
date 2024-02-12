---
title:                "Escrevendo para o erro padrão"
aliases:
- /pt/ruby/writing-to-standard-error/
date:                  2024-02-03T19:34:19.631260-07:00
model:                 gpt-4-0125-preview
simple_title:         "Escrevendo para o erro padrão"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/ruby/writing-to-standard-error.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## O Que & Por Que?
Escrever para o erro padrão (stderr) em Ruby é sobre direcionar mensagens de erro ou diagnósticos para um fluxo de saída separado, distinto da saída padrão (stdout). Os programadores fazem isso para diferenciar a saída regular do programa de erros e informações de depuração, facilitando o diagnóstico de problemas e a análise de logs.

## Como fazer:
A biblioteca padrão do Ruby oferece uma maneira simples de escrever para o stderr usando `$stderr` ou `STDERR`. Você não precisa de bibliotecas de terceiros para esta operação básica.

### Escrevendo uma mensagem simples para stderr:
```ruby
$stderr.puts "Erro: Arquivo não encontrado."
# Ou equivalentemente
STDERR.puts "Erro: Arquivo não encontrado."
```
Saída de exemplo (para stderr):
```
Erro: Arquivo não encontrado.
```

### Redirecionando stderr para um arquivo:
```ruby
File.open('error.log', 'w') do |file|
  STDERR.reopen(file)
  STDERR.puts "Falha ao abrir configuração."
end
```
Este trecho de código redireciona o stderr para um arquivo chamado `error.log`, e todos os erros escritos subsequentemente serão direcionados para lá até que o programa redefina o redirecionamento do stderr ou termine.

### Usando stderr com tratamento de exceção:
```ruby
begin
  # Simulando uma operação que poderia falhar, por ex., abrir um arquivo
  File.open('arquivo_inexistente.txt')
rescue Exception => e
  STDERR.puts "Ocorreu uma exceção: #{e.message}"
end
```
Saída de exemplo (para stderr):
```
Ocorreu uma exceção: No such file or directory @ rb_sysopen - arquivo_inexistente.txt
```

Embora os métodos integrados do Ruby para escrever para stderr sejam suficientes para muitas aplicações, para necessidades de registro de atividades mais complexas, você pode considerar a biblioteca padrão `logger` ou gems externas como `Log4r`. Estes fornecem mecanismos de registro configuráveis, incluindo níveis de severidade, formatação e a capacidade de escrever em várias saídas, incluindo arquivos, e-mail e mais.
