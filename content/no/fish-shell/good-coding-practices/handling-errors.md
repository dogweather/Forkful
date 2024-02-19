---
aliases:
- /no/fish-shell/handling-errors/
date: 2024-01-26 00:51:56.387782-07:00
description: "Feilh\xE5ndtering lar skriptet ditt takle det uventede p\xE5 en n\xE5\
  dig m\xE5te. Vi gj\xF8r det for \xE5 h\xE5ndtere feil uten \xE5 gj\xF8re brukernes\
  \ h\xE5r gr\xE5tt."
lastmod: 2024-02-18 23:08:54.358979
model: gpt-4-1106-preview
summary: "Feilh\xE5ndtering lar skriptet ditt takle det uventede p\xE5 en n\xE5dig\
  \ m\xE5te. Vi gj\xF8r det for \xE5 h\xE5ndtere feil uten \xE5 gj\xF8re brukernes\
  \ h\xE5r gr\xE5tt."
title: "Feilh\xE5ndtering"
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Feilhåndtering lar skriptet ditt takle det uventede på en nådig måte. Vi gjør det for å håndtere feil uten å gjøre brukernes hår grått.

## Hvordan:
For å fange feil i Fish, støtt deg på `status` kommandoen og betingelser. Si at `ping` mislykkes; slik kan du oppdage det:

```fish
ping -c 1 example.com
if not status is-success
    echo "Noe fiskete skjedde med ping."
end
```

Eksempelutdata hvis `ping` mislykkes:

```
Noe fiskete skjedde med ping.
```

For å håndtere en spesifikk feilkode, bruk `status --is`:

```fish
false
if status --is 1
    echo "Fanget en feil med kode 1."
end
```

Eksempelutdata:
```
Fanget en feil med kode 1.
```

For en mer robust tilnærming, vurder å bruke en funksjon:

```fish
function try_ping
    ping -c 1 example.com
    or begin
        echo "Ping mislyktes med status $status"
        return 1
    end
end

try_ping
```

## Dypdykk
Feilhåndtering i Fish matcher ikke `try/catch` paradigmet som du kanskje kjenner fra høyere nivå språk. I stedet har du greie utgangsstatusser gitt av `status` kommandoen.

Historisk sett, i Unix-lignende systemer, betyr en utgangsstatus på `0` suksess, mens hvilken som helst ikke-null verdi indikerer en feil, som ofte reflekterer forskjellige feilårsaker. Denne konvensjonen er brukt av de fleste kommandolinjeverktøyene og dermed, av Fish selv.

Alternativer til `status` sjekker i Fish inkluderer signalhåndtering via `trap` i andre skall, men Fish foretrekker mer eksplisitte statussjekker, fordi det er renere og mindre utsatt for bieffekter.

Når det gjelder gjennomføring, forblir feilhåndteringen i Fish enkel men kraftfull, i stor grad på grunn av sin ikke-blokkerende natur og vekt på klar syntaks, som vist i eksemplene. Feilkoder går pent sammen med funksjoner, noe som tillater modulær og lesbar feilhåndtering.

## Se Også
- Fish dokumentasjon om betingelser: https://fishshell.com/docs/current/language.html#conditionals
- Fish veiledning om feilhåndtering: https://fishshell.com/docs/current/tutorial.html#error-handling
