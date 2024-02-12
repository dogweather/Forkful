---
title:                "Nykyisen päivämäärän hankkiminen"
aliases:
- fi/ruby/getting-the-current-date.md
date:                  2024-02-03T19:10:41.777200-07:00
model:                 gpt-4-0125-preview
simple_title:         "Nykyisen päivämäärän hankkiminen"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/ruby/getting-the-current-date.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Mikä & Miksi?
Nykyisen päivämäärän hakeminen on olennainen tehtävä lähes missä tahansa ohjelmointiprojektissa, oli kyse sitten toimintojen lokituksesta sovelluksessa tai päiväleimoilla varustettujen raporttien tuottamisesta. Rubyssa tämä on helposti saavutettavissa käyttämällä standardikirjastoa, mikä yksinkertaistaa päivämääriä sisältäviä operaatioita.

## Kuinka:
Rubyn standardikirjasto sisältää `Date`- ja `Time`-luokat päivämäärien ja ajan käsittelyyn. Näin saat nykyisen päivämäärän:

```ruby
require 'date'

current_date = Date.today
puts current_date
```

Esimerkkikuloste: 
```
2023-04-12
```

Jos haluat sisällyttää ajan päivämäärän lisäksi, Rubyn `Time`-luokka on sopivampi:

```ruby
current_time = Time.now
puts current_time
```

Esimerkkikuloste: 
```
2023-04-12 14:33:07 +0200
```

Jos tarvitset lisätoiminnallisuutta, kuten aikavyöhykkeen hallintaa, saatat haluta käyttää kolmannen osapuolen gemiä, kuten `ActiveSupport` (osa Railseista, mutta voidaan käyttää itsenäisesti).

Lisää ensin `activesupport` Gemfileesi ja suorita `bundle install`:

```ruby
gem 'activesupport'
```

Käytä sitten sitä aikavyöhykkeiden käsittelyyn:

```ruby
require 'active_support/time'

Time.zone = 'Eastern Time (US & Canada)'  # Aseta haluamasi aikavyöhyke
current_time_with_zone = Time.zone.now
puts current_time_with_zone
```

Esimerkkikuloste:
```
Wed, 12 Apr 2023 08:33:07 EDT -04:00
```
