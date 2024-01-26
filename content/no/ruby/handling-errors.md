---
title:                "Feilhåndtering"
date:                  2024-01-26T00:56:46.110331-07:00
model:                 gpt-4-1106-preview
simple_title:         "Feilhåndtering"
programming_language: "Ruby"
category:             "Ruby"
tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/ruby/handling-errors.md"
---

{{< edit_this_page >}}

## Hva og hvorfor?

Feilhåndtering går ut på å forvente det uventede i koden - å håndtere feil og problemer på en smidig måte uten å krasje. Programmerere gjør dette for å kontrollere flyten når ting går galt, og for å holde brukeropplevelsen jevn.

## Hvordan gjøre det:

Ruby bruker `begin`, `rescue`, `ensure` og `end` for å håndtere feil. Du omslutter risikofylt kode med `begin` og `end`. Hvis en feil oppstår, trer `rescue` i kraft.

```Ruby
begin
  # Risikofylt kode kommer her.
  puts 10 / 0
rescue ZeroDivisionError => e
  puts "Oops! Du kan ikke gjøre det: #{e.message}"
ensure
  puts "Dette kjører alltid, uansett feil eller ikke."
end
```

Eksempel på utskrift:
```
Oops! Du kan ikke gjøre det: delt på 0
Dette kjører alltid, uansett feil eller ikke.
```

## Dypdykk

Historisk har feilhåndtering i programmeringsspråk utviklet seg betydelig, med tidlige språk som ofte hadde primitive eller ikke-eksisterende mekanismer. Rubys unntakshåndtering er inspirert av språk som Python og Smalltalk.

Alternativer til `begin-rescue` i Ruby inkluderer bruk av `rescue` i metodedefinisjoner eller å bruke `throw` og `catch` for ikke-standard flytkontroll, selv om de ikke brukes for typisk feilhåndtering.

En interessant detalj: Unntak i Ruby er objekter (instanser av `Exception`-klassen og dens etterkommere), så du kan definere egendefinerte feilklasser og gjøre mer enn bare å logge feil – du kan bære med deg rik tilstand rundt programmet for mer robust feilhåndtering.

## Se også

- Ruby-dokumentasjonen om unntak og feilhåndtering: [ruby-doc.org](https://ruby-doc.org/core-3.1.0/doc/syntax/exceptions_rdoc.html)
- En detaljert veiledning om beste praksiser for feilhåndtering i Ruby: [thoughtbot.com](https://thoughtbot.com/blog/rescue-standarderror-not-exception)