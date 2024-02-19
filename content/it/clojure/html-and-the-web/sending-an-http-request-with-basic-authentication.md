---
aliases:
- /it/clojure/sending-an-http-request-with-basic-authentication/
date: 2024-01-20 18:01:17.444016-07:00
description: "Inviare una richiesta HTTP con autenticazione di base significa passare\
  \ username e password in modo sicuro per accedere a una risorsa protetta. I\u2026"
lastmod: 2024-02-18 23:08:55.560730
model: gpt-4-1106-preview
summary: "Inviare una richiesta HTTP con autenticazione di base significa passare\
  \ username e password in modo sicuro per accedere a una risorsa protetta. I\u2026"
title: Inviare una richiesta http con autenticazione di base
---

{{< edit_this_page >}}

## Che cosa & perché?
Inviare una richiesta HTTP con autenticazione di base significa passare username e password in modo sicuro per accedere a una risorsa protetta. I programmatori lo fanno per interagire con servizi web che richiedono un livello di autorizzazione.

## Come fare:
```Clojure
(require '[clj-http.client :as client])

(defn fetch-protected-resource [url username password]
  (let [credentials (str username ":" password)
        encoded-credentials (-> credentials (.getBytes) java.util.Base64/getEncoder (.encodeToString))]
    (client/get url {:headers {"Authorization" (str "Basic " encoded-credentials)}})))

;; Uso:
(fetch-protected-resource "http://example.com" "mario.rossi" "password123")
```
Sample output:
```Clojure
{:status 200, :headers {...}, :body "..."}
```

## Approfondimento
L’autenticazione HTTP di base è un metodo antico ma semplice, incluso nello standard HTTP. Sostituita da soluzioni più moderne come OAuth, rimane utilizzata per la semplicità o legacy systems. Bisogna mandare le credenziali codificate in Base64, ma attenzione: senza HTTPS è insicuro. Nei progetti Clojure, `clj-http` è una scelta comune per fare richieste HTTP, con opzioni facili per l’autenticazione.

## Vedi anche
- Documentazione di `clj-http`: [https://github.com/dakrone/clj-http](https://github.com/dakrone/clj-http)
- Autenticazione HTTP di base su MDN: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication#basic_authentication_scheme](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication#basic_authentication_scheme)
