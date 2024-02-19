---
aliases:
- /sv/cpp/parsing-html/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:11:38.647184-07:00
description: "Att tolka HTML inneb\xE4r att bryta ner HTML-inneh\xE5ll till n\xE5\
  got som ett program kan f\xF6rst\xE5 och manipulera. Programmerare g\xF6r detta\
  \ f\xF6r att extrahera data,\u2026"
lastmod: 2024-02-18 23:08:52.081690
model: gpt-4-0125-preview
summary: "Att tolka HTML inneb\xE4r att bryta ner HTML-inneh\xE5ll till n\xE5got som\
  \ ett program kan f\xF6rst\xE5 och manipulera. Programmerare g\xF6r detta f\xF6\
  r att extrahera data,\u2026"
title: Tolka HTML
---

{{< edit_this_page >}}

## Vad & Varför?
Att tolka HTML innebär att bryta ner HTML-innehåll till något som ett program kan förstå och manipulera. Programmerare gör detta för att extrahera data, manipulera innehåll eller integrera webbskrapning i sina applikationer.

## Hur man gör:
C++ kommer inte med inbyggda funktioner för att tolka HTML. Du kommer ofta att använda ett bibliotek som Gumbo-parser från Google, eller något liknande. Här är ett snabbt exempel som använder Gumbo-parser:

```C++
#include <iostream>
#include <gumbo.h>

void search_for_links(GumboNode* nod) {
    if (nod->type != GUMBO_NODE_ELEMENT) {
        return;
    }
    if (nod->v.element.tag == GUMBO_TAG_A) {
        GumboAttribute* href = gumbo_get_attribute(&nod->v.element.attributes, "href");
        if (href) {
            std::cout << href->value << std::endl;
        }
    }
    GumboVector* barn = &nod->v.element.children;
    for (unsigned int i = 0; i < barn->length; ++i) {
        search_for_links(static_cast<GumboNode*>(barn->data[i]));
    }
}

int main() {
    const char* html = "<html><body><a href='https://example.com'>Länk</a></body></html>";
    GumboOutput* output = gumbo_parse(html);
    search_for_links(output->root);
    gumbo_destroy_output(&kGumboDefaultOptions, output);
    return 0;
}
```

Exempel på utdata:
```
https://example.com
```

## Djupdykning
Att tolka HTML har inte alltid varit okomplicerat i C++. Historiskt sett skulle programmerare använda regex eller handskrivna tolkare, båda är felbenägna och besvärliga. Nuförtiden hanterar robusta bibliotek som Gumbo-parser de intrikata detaljerna i tolkningen, vilket gör det enklare och mer pålitligt.

Alternativen inkluderar Tidy, MyHTML eller till och med integrering av C++ med Pythons BeautifulSoup via C++ `system`-funktionen eller inbäddade tolkar.

När det gäller implementering, konverterar dessa bibliotek HTML till ett Document Object Model (DOM)-träd. Genom att traversera och manipulera DOM kan användare extrahera och arbeta med data som demonstreras i Hur man gör-sektionen.

## Se även
- [Gumbo-parser GitHub-repositorium](https://github.com/google/gumbo-parser)
- [Lista över HTML-tolkningbibliotek](https://en.cppreference.com/w/c/experimental/dynamic)
- [Interoperabilitet mellan C++ och Python](https://docs.python.org/3/extending/embedding.html)
