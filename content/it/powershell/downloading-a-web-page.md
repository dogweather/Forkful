---
title:                "Scaricare una pagina web"
date:                  2024-01-20T17:44:23.682755-07:00
model:                 gpt-4-1106-preview
simple_title:         "Scaricare una pagina web"
programming_language: "PowerShell"
category:             "PowerShell"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/powershell/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## What & Why?
Scaricare una pagina web significa prendere il suo contenuto da internet e salvarlo localmente. I programmatori lo fanno per analizzare dati, testare applicazioni o archiviare informazioni.

## How to:
In PowerShell, `Invoke-WebRequest` è il tuo amico. Ecco come si usa:

```PowerShell
$response = Invoke-WebRequest -Uri "http://example.com"
$response.Content | Out-File -FilePath "pagina.html"
```

Dopo l'esecuzione, troverai "pagina.html" nella directory corrente, contenente il codice HTML della pagina web.

## Deep Dive
`Invoke-WebRequest` è una feature di PowerShell introdotta in versione 3.0. Alternativamente, potresti usare `System.Net.WebClient` in .NET, ma `Invoke-WebRequest` è più straight-forward per gli script.

Nella finestra PowerShell, `Invoke-WebRequest` gestisce diversi aspetti del web scraping prendendo anche i cookies e le sessioni. Tuttavia, per pagine JavaScript pesanti potresti aver bisogno di strumenti più avanzati come Selenium o Puppeteer per simulari un browser vero e proprio.

## See Also
- [PowerShell documentation for Invoke-WebRequest](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/invoke-webrequest)
- [Mozilla Developer Network (MDN) Web Docs for HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)
- [W3Schools HTML Tutorial](https://www.w3schools.com/html/)
