---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:12:01.333200-07:00
description: "\xC5 arbeide med JSON (JavaScript Object Notation) i Go inneb\xE6rer\
  \ koding og dekoding av data mellom Go-datastrukturer og JSON-format. Denne oppgaven\
  \ er\u2026"
lastmod: '2024-03-13T22:44:40.291136-06:00'
model: gpt-4-0125-preview
summary: "\xC5 arbeide med JSON (JavaScript Object Notation) i Go inneb\xE6rer koding\
  \ og dekoding av data mellom Go-datastrukturer og JSON-format."
title: Arbeide med JSON
weight: 38
---

## Hvordan:
I Go er pakken `encoding/json` din inngangsport til JSON-manipulering, som tilbyr mekanismer for å konvertere Go-datastrukturer til JSON (marshalling) og tilbake (unmarshalling). Nedenfor er grunnleggende eksempler for å komme i gang:

### Koding (Marshalling)
For å konvertere en Go-struct til JSON, kan du bruke `json.Marshal`. Vurder følgende Go-struct:

```go
package main

import (
    "encoding/json"
    "fmt"
    "log"
)

type Bruker struct {
    ID        int      `json:"id"`
    Brukernavn  string   `json:"username"`
    Språk []string `json:"languages"`
}

func main() {
    bruker := Bruker{1, "JohnDoe", []string{"Go", "JavaScript", "Python"}}
    brukerJSON, err := json.Marshal(bruker)
    if err != nil {
        log.Fatal(err)
    }
    fmt.Println(string(brukerJSON))
}
```

Utskrift:

```json
{"id":1,"username":"JohnDoe","languages":["Go","JavaScript","Python"]}
```

### Dekoding (Unmarshalling)
For å analysere JSON til en Go-datastruktur, bruk `json.Unmarshal`:

```go
package main

import (
    "encoding/json"
    "fmt"
    "log"
)

func main() {
    jsonStr := `{"id":1,"username":"JohnDoe","languages":["Go","JavaScript","Python"]}`
    var bruker Bruker
    err := json.Unmarshal([]byte(jsonStr), &bruker)
    if err != nil {
        log.Fatal(err)
    }
    fmt.Printf("%+v\n", bruker)
}
```

Gitt struct `Bruker` som før, parser denne koden JSON-strengen til en Bruker-instans.

Utskrift:

```go
{ID:1 Brukernavn:JohnDoe Språk:[Go JavaScript Python]}
```

## Dypdykk
Pakken `encoding/json` i Go tilbyr et greit API som abstraherer mye av kompleksiteten involvert i JSON-manipulering. Introdsert tidlig i utviklingen av Go, reflekterer denne pakken Go sin filosofi om enkelhet og effektivitet. Men, bruken av refleksjon av `encoding/json` for å inspisere og modifisere structs ved kjøretid, kan lede til mindre enn optimal ytelse i CPU-intensive scenarioer.

Alternativer som `json-iterator/go` og `ffjson` har dukket opp, og tilbyr raskere JSON-behandling ved å generere statisk marshalling og unmarshalling-kode. Imidlertid forblir `encoding/json` den mest brukte pakken på grunn av dens enkelhet, robusthet og det faktum at den er en del av standardbiblioteket, slik at den sikrer kompatibilitet og stabilitet på tvers av Go-versjoner.

På tross av sin relativt langsommere ytelse, gjør brukervennligheten og integrasjonen med Gos typesystem `encoding/json` passende for de fleste applikasjoner. For de som jobber i kontekster hvor ytelse er av største viktighet, kan det være verdt å utforske eksterne biblioteker, men for mange treffer standardbiblioteket den rette balansen mellom hastighet, enkelhet og pålitelighet.
