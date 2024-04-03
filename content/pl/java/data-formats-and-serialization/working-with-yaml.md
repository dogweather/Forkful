---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:25:40.310061-07:00
description: "YAML, skr\xF3t od \"YAML Ain't Markup Language\", to standard serializacji\
  \ danych, kt\xF3ry jest czytelny dla cz\u0142owieka i kt\xF3rego programi\u015B\
  ci u\u017Cywaj\u0105 do plik\xF3w\u2026"
lastmod: '2024-03-13T22:44:35.299223-06:00'
model: gpt-4-0125-preview
summary: "YAML, skr\xF3t od \"YAML Ain't Markup Language\", to standard serializacji\
  \ danych, kt\xF3ry jest czytelny dla cz\u0142owieka i kt\xF3rego programi\u015B\
  ci u\u017Cywaj\u0105 do plik\xF3w konfiguracyjnych, zrzut\xF3w danych oraz transmisji\
  \ danych mi\u0119dzy j\u0119zykami."
title: Praca z YAML
weight: 41
---

## Jak to zrobić:
W Javie można pracować z plikami YAML za pomocą bibliotek firm trzecich, ponieważ Java Standard Edition nie zawiera wbudowanego wsparcia dla YAML. Jedną z popularnych bibliotek jest SnakeYAML, która umożliwia łatwe parsowanie i generowanie danych YAML.

### Konfiguracja SnakeYAML
Po pierwsze, dołącz SnakeYAML do swojego projektu. Jeśli używasz Mavena, dodaj następującą zależność do swojego pliku `pom.xml`:

```xml
<dependency>
    <groupId>org.yaml</groupId>
    <artifactId>snakeyaml</artifactId>
    <version>1.30</version>
</dependency>
```

### Odczytywanie YAML
```java
import org.yaml.snakeyaml.Yaml;
import java.io.InputStream;
import java.util.Map;

public class ReadYamlExample {
    public static void main(String[] args) {
        Yaml yaml = new Yaml();
        try (InputStream inputStream = ReadYamlExample.class
                .getClassLoader()
                .getResourceAsStream("config.yml")) {
            Map<String, Object> data = yaml.load(inputStream);
            System.out.println(data);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```
Zakładając, że `config.yml` wygląda tak:
```yaml
name: Example
version: 1.0
features:
  - login
  - signup
```
Wynik będzie:
```
{name=Example, version=1.0, features=[login, signup]}
```

### Zapisywanie YAML
Aby wygenerować YAML z obiektów Java, użyj metody `dump` dostarczonej przez SnakeYAML:
```java
import org.yaml.snakeyaml.Yaml;
import java.util.Arrays;
import java.util.LinkedHashMap;
import java.util.Map;

public class WriteYamlExample {
    public static void main(String[] args) {
        Map<String, Object> data = new LinkedHashMap<>();
        data.put("name", "Example");
        data.put("version", 1.0);
        data.put("features", Arrays.asList("login", "signup"));

        Yaml yaml = new Yaml();
        String output = yaml.dump(data);
        System.out.println(output);
    }
}
```
Wygeneruje to i wydrukuje następującą zawartość YAML:
```yaml
name: Example
version: 1.0
features:
- login
- signup
```
Korzystając z SnakeYAML, programiści Java mogą łatwo zintegrować analizę i generowanie YAML do swoich aplikacji, korzystając z czytelności i prostoty YAML do celów konfiguracyjnych i wymiany danych.
