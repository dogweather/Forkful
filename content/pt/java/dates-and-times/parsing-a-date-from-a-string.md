---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:14:20.408512-07:00
description: "Analisar uma data a partir de uma string envolve converter a representa\xE7\
  \xE3o textual de uma data e hora em um objeto `Date` ou em um objeto `LocalDateTime`\u2026"
lastmod: '2024-03-13T22:44:46.465266-06:00'
model: gpt-4-0125-preview
summary: "Analisar uma data a partir de uma string envolve converter a representa\xE7\
  \xE3o textual de uma data e hora em um objeto `Date` ou em um objeto `LocalDateTime`\
  \ mais moderno."
title: Analisando uma data a partir de uma string
weight: 30
---

## Como Fazer:


### Usando o pacote `java.time` (Recomendado no Java 8 e posteriores):
```java
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

public class DateParser {
    public static void main(String[] args) {
        String dateString = "2023-04-30";
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd");
        LocalDate date = LocalDate.parse(dateString, formatter);
        System.out.println(date); // Saída: 2023-04-30
    }
}
```

### Usando `SimpleDateFormat` (Abordagem Antiga):
```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class DateParser {
    public static void main(String[] args) {
        String dateString = "30/04/2023";
        SimpleDateFormat formatter = new SimpleDateFormat("dd/MM/yyyy");
        try {
            Date date = formatter.parse(dateString);
            System.out.println(date); // O formato da saída depende do formato padrão do seu sistema
        } catch (ParseException e) {
            e.printStackTrace();
        }
    }
}
```

### Usando Bibliotecas de Terceiros (ex.: Joda-Time):
Joda-Time tem sido uma biblioteca de terceiros significativa, mas agora está em modo de manutenção devido à introdução do pacote `java.time` no Java 8. Contudo, para aqueles que usam versões do Java anteriores ao 8, Joda-Time é uma boa escolha.
```java
import org.joda.time.LocalDate;
import org.joda.time.format.DateTimeFormat;
import org.joda.time.format.DateTimeFormatter;

public class DateParser {
    public static void main(String[] args) {
        String dateString = "2023-04-30";
        DateTimeFormatter formatter = DateTimeFormat.forPattern("yyyy-MM-dd");
        LocalDate date = LocalDate.parse(dateString, formatter);
        System.out.println(date); // Saída: 2023-04-30
    }
}
```
Note que, ao trabalhar com datas, sempre esteja ciente das configurações de fuso horário se estiver analisando ou formatando datas-horas, em vez de apenas datas.
