---
aliases:
- /fi/ruby/calculating-a-date-in-the-future-or-past/
date: 2024-01-20 17:31:50.173067-07:00
description: "\"Mik\xE4 & Miksi?\" Ajan laskeminen tulevaisuuteen tai menneisyyteen\
  \ tarkoittaa p\xE4iv\xE4m\xE4\xE4r\xE4n laskemista n p\xE4iv\xE4\xE4, viikkoa, kuukautta\
  \ tai vuotta ennen tai\u2026"
lastmod: 2024-02-18 23:09:08.197527
model: gpt-4-1106-preview
summary: "\"Mik\xE4 & Miksi?\" Ajan laskeminen tulevaisuuteen tai menneisyyteen tarkoittaa\
  \ p\xE4iv\xE4m\xE4\xE4r\xE4n laskemista n p\xE4iv\xE4\xE4, viikkoa, kuukautta tai\
  \ vuotta ennen tai\u2026"
title: "Tulevan tai menneen p\xE4iv\xE4m\xE4\xE4r\xE4n laskeminen"
---

{{< edit_this_page >}}

## What & Why?
"Mikä & Miksi?"
Ajan laskeminen tulevaisuuteen tai menneisyyteen tarkoittaa päivämäärän laskemista n päivää, viikkoa, kuukautta tai vuotta ennen tai jälkeen annetun päivämäärän. Koodaajat tekevät tätä aikataulujen hallintaan, ajanjaksojen seurantaan ja määräaikojen asettamiseen.

## How to:
"Kuinka tehdä:"
```Ruby
require 'date'

# Tänään
today = Date.today
puts "Today is: #{today}"

# 5 päivää tulevaisuudessa
future_date = today + 5
puts "Five days from today is: #{future_date}"

# 2 viikkoa menneisyydessä
past_date = today - 14
puts "Two weeks ago was: #{past_date}"

# 3 kuukautta tulevaisuudessa, käyttäen >> operaattoria
future_date_months = today >> 3
puts "Three months from today is: #{future_date_months}"

# 1 vuosi menneisyydessä, käyttäen << operaattoria
past_date_years = today << 1
puts "One year ago was: #{past_date_years}"
```
Sample output:
```
Today is: 2023-04-01
Five days from today is: 2023-04-06
Two weeks ago was: 2023-03-18
Three months from today is: 2023-07-01
One year ago was: 2022-04-01
```

## Deep Dive:
"Syväsukellus":
Ajan laskeminen ei ole uusi tarve; sitä on tehty vuosisatoja. Rubyssa ajan laskeminen on tehty helpoksi Date- ja Time-luokilla. Vaihtoehtoisia tapoja sisältävät käyttämisen time-lisäkirjastossa olevia Time-olioita tai kolmannen osapuolen kirjastoja, kuten 'active_support' Rails-kehyksestä, joka tarjoaa metodeja kuten `3.days.from_now`.
Rubyssa päivämäärää yritetään käsitellä universaalisti huomioiden aikavyöhykkeet ja karkausvuodet. Implisiittisesti oletuksena on kansainvälinen Gregoriaaninen kalenteri.

## See Also:
"Näihin kannattaa tutustua lisää":
- Ruby Date documentation: https://ruby-doc.org/stdlib/libdoc/date/rdoc/Date.html
- Ruby Time documentation: https://ruby-doc.org/core-2.7.0/Time.html
- ActiveSupport::Duration in Rails for more complex date calculations: https://api.rubyonrails.org/classes/ActiveSupport/Duration.html
