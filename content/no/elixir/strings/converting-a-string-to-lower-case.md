---
date: 2024-01-20 17:38:28.696065-07:00
description: "Konvertering av strenger til sm\xE5 bokstaver betyr \xE5 endre alle\
  \ tegn i en tekststreng til deres sm\xE5 bokstavversjon. Programmerere gj\xF8r dette\
  \ for \xE5\u2026"
lastmod: '2024-03-13T22:44:40.430634-06:00'
model: gpt-4-1106-preview
summary: "Konvertering av strenger til sm\xE5 bokstaver betyr \xE5 endre alle tegn\
  \ i en tekststreng til deres sm\xE5 bokstavversjon."
title: "Konvertere en streng til sm\xE5 bokstaver"
weight: 4
---

## How to:
I Elixir bruker vi `String.downcase/2` for å konvertere strenger til små bokstaver. Her er et eksempel:

```elixir
original = "Hei Verden!"
lowercased = String.downcase(original)
IO.puts lowercased
```

Forventet utskrift:

```
hei verden!
```

Du kan også angi et bestemt språklokale for å sikre at spesifikke tegnsettsregler følges:

```elixir
norwegian_text = "ÆØÅ Ære være Norge!"
lowercased_norwegian = String.downcase(norwegian_text, :norwegian)
IO.puts lowercased_norwegian
```

Forventet utskrift:

```
æøå ære være norge!
```

## Deep Dive
Funksjonen `String.downcase/2` har eksistert siden de tidlige dagene av Elixir og gjør bruk av Unicode for å sikre riktig håndtering av forskjellige språk. Alternativene til `String.downcase/2` inkluderer manuell manipulering av strengene, men dette er sjelden effektivt og kan føre til feil i språk med komplekse tegnsettsregler, som tyrkisk.

Implementeringen bruker utfordringen med Unicode normalization, som transformere tekst til en stabil form som kan sammenlignes binært. Denne prosessen håndterer ikke bare ASCII-tegn, men også internasjonale tegn og symboler korrekt.

Elixir's `String` modul bruker Erlang's `:unicode` modul bak kulissene, noe som gir ytterligere robusthet i håndteringen av internasjonalisert tekst.

## See Also
- [Elixir String Module Documentation](https://hexdocs.pm/elixir/String.html)
- [Unicode Normalization Forms](http://unicode.org/reports/tr15/)
- [Erlang's :unicode Module Documentation](http://erlang.org/doc/man/unicode.html)
