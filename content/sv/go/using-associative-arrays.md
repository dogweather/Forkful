---
title:                "Använda associativa arrayer"
aliases:
- sv/go/using-associative-arrays.md
date:                  2024-02-03T18:10:53.455404-07:00
model:                 gpt-4-0125-preview
simple_title:         "Använda associativa arrayer"
tag:                  "Data Structures"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/go/using-associative-arrays.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Vad & Varför?

Associerade arrayer, kända som maps i Go, gör det möjligt för dig att lagra nyckel-värdepar där varje unik nyckel mappas till ett värde. Programmerare använder maps för effektiv datahämtning, modifiering och för att underhålla en samling av element som snabbt kan nås med unika nycklar.

## Hur:

Att skapa och initiera en map i Go kan göras på olika sätt. Här är ett grundläggande exempel för att komma igång:

```go
package main

import "fmt"

func main() {
    // Deklarera och initiera en map
    colors := map[string]string{
        "red":   "#FF0000",
        "green": "#00FF00",
        "blue":  "#0000FF",
    }

    fmt.Println(colors)
    // Utdata: map[blue:#0000FF green:#00FF00 red:#FF0000]
}
```

För att lägga till eller uppdatera element tilldelar du ett värde till en nyckel så här:

```go
colors["white"] = "#FFFFFF"
fmt.Println(colors)
// Utdata: map[blue:#0000FF green:#00FF00 red:#FF0000 white:#FFFFFF]
```

Att komma åt ett värde med dess nyckel är enkelt:

```go
fmt.Println("Hexkoden för röd är:", colors["red"])
// Utdata: Hexkoden för röd är: #FF0000
```

För att ta bort ett element använder du funktionen `delete`:

```go
delete(colors, "red")
fmt.Println(colors)
// Utdata: map[blue:#0000FF green:#00FF00 white:#FFFFFF]
```

Att iterera över en map görs med en for-loop:

```go
for color, hex := range colors {
    fmt.Printf("Nyckel: %s Värde: %s\n", color, hex)
}
```

Kom ihåg, maps i Go är oordnade. Ordningen på iterationen är inte garanterad.

## Djupdykning

I Go är maps implementerade som hashtabeller. Varje post i mappen består av två delar: en nyckel och ett värde. Nyckeln hashas för att lagra posten, vilket möjliggör operationer i konstant tid för en liten uppsättning data och genomsnittlig tidskomplexitet O(1) med korrekt hashing, som kan förvärras till O(n) i värsta fall med många hash-kollisioner.

En viktig not för nya Go-programmerare är att map-typer är referenstyper. Detta innebär att när du passerar en map till en funktion, är alla ändringar som görs på mappen inom den funktionen synliga för anroparen. Detta skiljer sig från, säg, att passera en struktur till en funktion, där strukturen kopieras om den inte överförs genom en pekare.

Även om maps är otroligt mångsidiga och effektiva för de flesta användningsfall som involverar associerade arrayer, kan det i prestandakritiska applikationer vara fördelaktigt att använda datastrukturer med mer förutsägbara prestandaegenskaper, särskilt om nyckeldistributioner kan orsaka frekventa kollisioner.

Ett annat alternativ att överväga är `sync.Map`, tillgängligt sedan Go 1.9, avsett för användningsfall där nycklar bara skrivs en gång men läses många gånger och erbjuder effektivitetsförbättringar i dessa scenarier. Dock är för konventionella Go-applikationer vanlig map-användning idiomatic och ofta den rekommenderade metoden för sin enkelhet och direkta stöd i språket.
