---
date: 2024-01-20 17:44:37.638039-07:00
description: "Scaricare una pagina web significa prelevare dati da un sito e salvarli\
  \ localmente. I programmatori lo fanno per analizzare il contenuto, testare le\u2026"
lastmod: '2024-03-13T22:44:43.515532-06:00'
model: gpt-4-1106-preview
summary: Scaricare una pagina web significa prelevare dati da un sito e salvarli localmente.
title: Scaricare una pagina web
weight: 42
---

## How to:
Per scaricare una pagina web con PHP, puoi usare `file_get_contents` o cURL. Ecco un esempio semplice:

```PHP
<?php
$url = "http://www.esempio.com";
$paginaWeb = file_get_contents($url);

if ($paginaWeb !== false) {
    // Fai qualcosa con $paginaWeb
    echo "Pagina scaricata con successo!";
} else {
    echo "Errore nel download della pagina.";
}
?>
```

Assicurati che `allow_url_fopen` sia abilitato nel file `php.ini` per usare `file_get_contents` con URL.

Se preferisci cURL per maggiore flessibilità e controllo:

```PHP
<?php
$curl = curl_init("http://www.esempio.com");
curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
$paginaWeb = curl_exec($curl);

if ($paginaWeb !== false) {
    // Fai qualcosa con $paginaWeb
    echo "Pagina scaricata con successo!";
} else {
    echo "Errore: " . curl_error($curl);
}

curl_close($curl);
?>
```

Output per entrambi i casi, se la pagina è stata scaricata con successo:
```
Pagina scaricata con successo!
```

## Deep Dive
Prima di PHP 4.3.0, `file_get_contents` non era disponibile, quindi cURL era il metodo principale per scaricare pagine web. cURL offre opzioni avanzate come la gestione di cookie, header HTTP personalizzati, timeout, e autenticazione.

Un'alternativa a questi metodi è la libreria Guzzle, un client HTTP PHP che semplifica il lavoro con le richieste HTTP.

Quando scarichi una pagina, considera la legalità (rispetta `robots.txt`) e l'etica (non sovraccaricare il server).

## See Also
- Documentazione ufficiale PHP per `file_get_contents`: https://www.php.net/manual/en/function.file-get-contents.php
- Documentazione ufficiale PHP per cURL: https://www.php.net/manual/en/book.curl.php
- Guzzle, client HTTP PHP: http://docs.guzzlephp.org/en/stable/
- robots.txt: https://www.robotstxt.org/
