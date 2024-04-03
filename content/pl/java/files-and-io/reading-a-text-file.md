---
date: 2024-01-20 17:54:29.807549-07:00
description: "Czytanie pliku tekstowego to proces pozyskiwania danych z zapisanego\
  \ tekstu. Programi\u015Bci robi\u0105 to, by obs\u0142u\u017Cy\u0107 informacje\
  \ \u2013 konfigurowa\u0107 aplikacje,\u2026"
lastmod: '2024-03-13T22:44:35.295616-06:00'
model: gpt-4-1106-preview
summary: Czytanie pliku tekstowego to proces pozyskiwania danych z zapisanego tekstu.
title: Odczytywanie pliku tekstowego
weight: 22
---

## Jak to zrobić:
Do wczytywania plików tekstowych w Javie wykorzystujemy klasę `Files` z pakietu `java.nio.file`, która oferuje metodę `readAllLines`. Poniżej prosty przykład:

```java
import java.nio.file.Files;
import java.nio.file.Path;
import java.util.List;

public class ReadTextFileExample {
    public static void main(String[] args) {
        try {
            Path filePath = Path.of("example.txt");
            List<String> lines = Files.readAllLines(filePath);
            lines.forEach(System.out::println);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

Przy założeniu, że w pliku `example.txt` znajduje się:

```
Witaj w pliku tekstowym.
To jest druga linia.
```

Wynik wykonania programu:

```
Witaj w pliku tekstowym.
To jest druga linia.
```

## Pogłębiona wiedza
Czytanie plików tekstowych ewoluowało w Javie. Kiedyś dominowała klasa `FileReader` w połączeniu z `BufferedReader`. Dziś preferujemy `Files` z `java.nio.file` dla lepszej wydajności i prostoty.

Alternatywy to na przykład `Scanner` do czytania danych z różnych źródeł włączając pliki, czy `FileInputStream` dla binarnych danych. 

Ważne: Obsługa wyjątków i kodowania to kluczowe aspekty. `readAllLines` domyślnie używa UTF-8, co jest bezpieczne dla większości języków, wliczając polski.

## Zobacz również
- Dokumentacja `Files.readAllLines`: https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/nio/file/Files.html#readAllLines(java.nio.file.Path)
- Tutorial Oracle do NIO.2 (nowe wejście/wyjście): https://docs.oracle.com/javase/tutorial/essential/io/fileio.html
- Ewolucja wejścia/wyjścia w Javie (ang.): https://www.baeldung.com/java-io-vs-nio
