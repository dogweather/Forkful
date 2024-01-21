---
title:                "Komennoriviparametrien lukeminen"
date:                  2024-01-20T17:56:52.050431-07:00
model:                 gpt-4-1106-preview
simple_title:         "Komennoriviparametrien lukeminen"
programming_language: "Ruby"
category:             "Ruby"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/ruby/reading-command-line-arguments.md"
---

{{< edit_this_page >}}

## What & Why? (Mitä & Miksi?)
Komentoriviparametrit ovat tietoja, jotka siirtyvät ohjelmaasi käynnistyksen yhteydessä. Niitä käytetään muokkaamaan ohjelman toimintaa lennosta ja antamaan tarvittava sisältö ilman kovakoodausta.

## How to: (Kuinka tehdä:)
```ruby
# example.rb
ARGV.each_with_index do |arg, index|
  puts "Argumentti #{index}: #{arg}"
end
```
Kun ajat `ruby example.rb ensimmäinen toinen kolmas`, saat:
```
Argumentti 0: ensimmäinen
Argumentti 1: toinen
Argumentti 2: kolmas
```

## Deep Dive (Sukellus syvemmälle)
Komentoriviparametrit ovat olleet osa ohjelmointia siitä lähtien, kun käyttöliittymät olivat tekstipohjaisia. Rubyssa `ARGV` on globaali muuttuja, joka sisältää komentoriviltä saadut argumentit (string-muodossa) taulukossa. Ei ole harvinaista nähdä skriptejä, joissa `ARGV` purkautuu käyttäen esimerkiksi `shift`- tai `pop`-metodeja, jotta voidaan käsitellä argumentteja yksi kerrallaan. Jos haluat ohittaa argumenttien käsittelyn ja käyttää valmiita ratkaisuja, voit hyödyntää optioparserin kaltaisia kirjastoja, jotka tekevät komentorivin argumenttien hallinnasta elegantimpaa ja monipuolisempaa.

## See Also (Katso myös)
- OptionParser-kirjaston esittely: [Ruby Docs OptionParser](https://www.ruby-doc.org/stdlib-2.7.0/libdoc/optparse/rdoc/OptionParser.html)