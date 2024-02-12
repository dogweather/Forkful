---
title:                "Schrijven naar standaardfout"
aliases:
- nl/ruby/writing-to-standard-error.md
date:                  2024-01-28T22:13:41.666380-07:00
model:                 gpt-4-0125-preview
simple_title:         "Schrijven naar standaardfout"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/ruby/writing-to-standard-error.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Standaardfout (`stderr`) is een stroom die los staat van standaarduitvoer (`stdout`) en wordt voornamelijk gebruikt voor het uitgeven van foutmeldingen of diagnostiek. Programmeurs gebruiken het om te voorkomen dat foutmeldingen zich mengen met reguliere programma-uitvoer, wat helpt bij zowel debugging als outputverwerking.

## Hoe doe je dat:
In Ruby kunt je naar standaardfout schrijven met `$stderr.puts` of de verkorte vorm `STDERR.puts`. Hier is een snel voorbeeld:

```ruby
puts "Dit gaat naar standaarduitvoer."
$stderr.puts "Dit gaat naar standaardfout."

# Verkorte versie:
STDERR.puts "Dit gaat ook naar standaardfout."
```

Open je terminal, voer het script uit, en merk op dat alles standaard toch samengevoegd wordt weergegeven. Het is nodig om te redirecten om de stromen te scheiden. Zo kun je dat doen:

```shell
ruby jouw_script.rb >uitvoer.txt 2>fout.txt
```

Dit commando redirect de standaarduitvoer naar `uitvoer.txt` en standaardfout naar `fout.txt`.

## Diepere Duik
Het concept van `stderr` gaat terug tot de vroegste dagen van Unix. Het is ontworpen voor foutmeldingen om ervoor te zorgen dat ze zichtbaar zijn, zelfs als `stdout` wordt geredirect. Hoewel `$stderr.puts` en `STDERR.puts` gebruikelijk zijn in Ruby, zijn er andere manieren om naar `stderr` te schrijven, zoals `warn` gebruiken voor het schrijven van waarschuwingen of lagere niveau API's zoals `$stderr.write`. Wat implementatie betreft, is `stderr` standaard ongebufferd, wat zorgt voor onmiddellijke uitvoer, terwijl `stdout` typisch gebufferd is.

## Zie Ook
- Ruby documentatie over I/O: [https://ruby-doc.org/core-3.1.2/IO.html](https://ruby-doc.org/core-3.1.2/IO.html)
- De Open Group Basis Specificaties (UNIX standaardstromen): [https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap08.html](https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap08.html)
- Begrip van omleidingen in shellscripts: [https://www.gnu.org/software/bash/manual/html_node/Redirections.html](https://www.gnu.org/software/bash/manual/html_node/Redirections.html)
