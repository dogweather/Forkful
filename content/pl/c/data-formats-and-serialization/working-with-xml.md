---
title:                "Praca z XML"
date:                  2024-02-03T18:13:02.919077-07:00
model:                 gpt-4-0125-preview
simple_title:         "Praca z XML"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/c/working-with-xml.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?

Praca z XML w języku C wiąże się z parsowaniem, wyszukiwaniem i manipulowaniem dokumentami XML za pomocą różnych bibliotek. Programiści angażują się w pracę z XML ze względu na jego powszechne zastosowanie w usługach internetowych, plikach konfiguracyjnych i wymianie danych pomiędzy różnymi systemami, co wymaga umiejętności efektywnego radzenia sobie z XML w celu robustowego rozwoju aplikacji.

## Jak to zrobić:

C nie ma wbudowanego wsparcia dla XML, więc będziesz musiał użyć zewnętrznych bibliotek. Jednym z popularnych wyborów jest `libxml2`, stabilna i bogata w funkcje biblioteka. Oto jak odczytać i zanalizować plik XML przy użyciu `libxml2`.

Najpierw upewnij się, że masz zainstalowane `libxml2` w swoim systemie. Może być konieczne jego zainstalowanie za pomocą menedżera pakietów (np. `apt-get install libxml2-dev` na systemach Debian).

Następnie, dołącz nagłówek `libxml2` do swojego programu w C:

```c
#include <libxml/parser.h>
#include <libxml/tree.h>
```

Teraz, napiszmy prosty program do parsowania pliku XML i wypisywania nazw elementów pierwszego poziomu:

```c
#include <stdio.h>
#include <libxml/parser.h>
#include <libxml/tree.h>

int main(void) {
    xmlDoc *document = NULL;
    xmlNode *root_element = NULL;

    // Inicjalizacja biblioteki i sprawdzanie potencjalnych niezgodności ABI
    LIBXML_TEST_VERSION

    // Parsowanie pliku i uzyskanie modelu DOM
    document = xmlReadFile("your_file.xml", NULL, 0);

    if (document == NULL) {
        printf("Nie udało się zanalizować pliku XML\n");
        return -1;
    }

    // Uzyskanie węzła elementu głównego
    root_element = xmlDocGetRootElement(document);

    for (xmlNode *currentNode = root_element; currentNode; currentNode = currentNode->next) {
        if (currentNode->type == XML_ELEMENT_NODE) {
            printf("Typ węzła: Element, nazwa: %s\n", currentNode->name);
        }
    }

    // Zwolnienie pamięci przydzielonej dla parsera i modelu DOM
    xmlFreeDoc(document);

    // Sprzątanie i sprawdzanie wycieków
    xmlCleanupParser();
    xmlMemoryDump(); // Opcjonalnie

    return 0;
}
```

Aby skompilować ten program, upewnij się, że linkujesz z `libxml2`:

```sh
gcc -o xml_example xml_example.c $(xml2-config --cflags --libs)
```

Zakładając, że masz plik XML o nazwie `your_file.xml`, uruchomienie skompilowanego programu powinno wydrukować nazwy jego elementów pierwszego poziomu.

## Pogłębiona analiza

Interakcja między C a XML to opowieść o łączeniu dwóch bardzo różnych światów: strukturalnego, na poziomie bajtów, proceduralnego paradygmatu C oraz hierarchicznego, przegadanych i ukierunkowanego na dokumenty modelu XML. Integracja możliwości obsługi XML do programów w C pozwala programistom wykorzystać mocne strony C - takie jak szybkość i niskopoziomowy dostęp do pamięci - do efektywnego parsowania i manipulowania dokumentami XML.

`libxml2`, rozwijana jako część projektu GNOME, wyłoniła się jako de facto standard do przetwarzania XML w C ze względu na jej wszechstronne wsparcie dla standardów XML i wydajność. Jest owocem lat wysiłków rozwojowych i wkładu społeczności, co czyni ją solidną i efektywną w większości zadań związanych z XML.

Chociaż `libxml2` oferuje potężne możliwości, warto zauważyć, że złożoność parsowania i manipulowania XML może wprowadzić znaczne obciążenie. W scenariuszach, gdzie przegadane i złożone XML są nieuzasadnione, alternatywy takie jak JSON mogą być preferowane dla wymiany danych. Niemniej jednak, dla aplikacji zorientowanych na XML lub środowisk, gdzie użycie XML jest zakorzenione, opanowanie wykorzystania `libxml2` w C otwiera możliwość pracy z szerokim zakresem dokumentów XML i API, łącząc luki między językiem programowania C a światem przetwarzania zorganizowanych dokumentów.
