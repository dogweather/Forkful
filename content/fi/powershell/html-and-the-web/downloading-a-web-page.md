---
date: 2024-01-20 17:44:36.922313-07:00
description: "Lataaminen on verkkosivun datan siirt\xE4mist\xE4 paikalliselle koneelle.\
  \ Ohjelmoijat tekev\xE4t sen tiedon k\xE4sittely\xE4 tai automatisointia varten."
lastmod: '2024-03-13T22:44:56.781233-06:00'
model: gpt-4-1106-preview
summary: "Lataaminen on verkkosivun datan siirt\xE4mist\xE4 paikalliselle koneelle."
title: Verkkosivun lataaminen
weight: 42
---

## How to:
Aloita. Avaa PowerShell. Käytä Invoke-WebRequest -komentoa:

```PowerShell
$response = Invoke-WebRequest -Uri 'http://example.com'
$response.Content
```

Esimerkkitulostus näyttää ladatun verkkosivun HTML-koodin.

## Deep Dive
PowerShellissa sivun lataaminen liittyy Invoke-WebRequest -komennon käyttöön, joka esiteltiin versiossa 3.0. Vaihtoehtona voit käyttää System.Net.WebClient -luokkaa, mutta moderneissa skripteissä Invoke-WebRequest on suositumpi ratkaisu, koska se on suunniteltu nimenomaan PowerShellin kanssa yhteensopivaksi. Tämän komennon kautta saat paitsi sivun sisällön, myös pääsyyn otsakkeisiin, kekseihin ja HTTP-vastauksen statuksiin.

## See Also
- Microsoftin PowerShell-dokumentaatio: [Invoke-WebRequest](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/invoke-webrequest)
- Lisätietoja HTTP-protokollasta: [HTTP - MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/HTTP)
