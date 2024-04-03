---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:34:18.014625-07:00
description: "\xC5 skrive til standardfeil (stderr) i Ruby handler om \xE5 dirigere\
  \ feilmeldinger eller diagnostikk til en separat utstr\xF8m, forskjellig fra standardutgangen\u2026"
lastmod: '2024-03-13T22:44:41.349646-06:00'
model: gpt-4-0125-preview
summary: "\xC5 skrive til standardfeil (stderr) i Ruby handler om \xE5 dirigere feilmeldinger\
  \ eller diagnostikk til en separat utstr\xF8m, forskjellig fra standardutgangen\
  \ (stdout)."
title: Skriving til standardfeil
weight: 25
---

## Hvordan:
Rubys standardbibliotek gir en enkel måte å skrive til stderr ved å bruke `$stderr` eller `STDERR`. Du trenger ikke tredjepartsbiblioteker for denne grunnleggende operasjonen.

### Skrive en enkel melding til stderr:
```ruby
$stderr.puts "Feil: Fil ikke funnet."
# Eller tilsvarende
STDERR.puts "Feil: Fil ikke funnet."
```
Eksempelutskrift (til stderr):
```
Feil: Fil ikke funnet.
```

### Omdirigere stderr til en fil:
```ruby
File.open('error.log', 'w') do |file|
  STDERR.reopen(file)
  STDERR.puts "Mislyktes i å åpne konfigurasjonen."
end
```
Denne kodesnutten omdirigerer stderr til en fil med navnet `error.log`, og alle påfølgende skrevne feil vil bli utskrevet der til programmet tilbakestiller omdirigeringen av stderr eller avslutter.

### Bruke stderr med unntakshåndtering:
```ruby
begin
  # Simulerer en operasjon som kunne feile, f.eks., å åpne en fil
  File.open('nonexistent_file.txt')
rescue Exception => e
  STDERR.puts "Unntak oppsto: #{e.message}"
end
```
Eksempelutskrift (til stderr):
```
Unntak oppsto: No such file or directory @ rb_sysopen - nonexistent_file.txt
```

Selv om Rubys innebygde metoder for å skrive til stderr er tilstrekkelige for mange applikasjoner, kan du vurdere standardbiblioteket `logger` eller eksterne gems som `Log4r` for mer komplekse loggingsbehov. Disse tilbyr konfigurerbare loggingsmekanismer, inkludert alvorlighetsnivåer, formatering og muligheten til å skrive til ulike utdata, inkludert filer, e-post og mer.
