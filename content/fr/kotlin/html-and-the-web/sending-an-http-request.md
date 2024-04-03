---
date: 2024-01-20 18:00:12.137575-07:00
description: "Envoyer une requ\xEAte HTTP, c'est demander des donn\xE9es \xE0 un serveur\
  \ web. Les programmeurs en ont besoin pour les applications qui bouffent de l'info\
  \ en\u2026"
lastmod: '2024-03-13T22:44:57.735375-06:00'
model: gpt-4-1106-preview
summary: "Envoyer une requ\xEAte HTTP, c'est demander des donn\xE9es \xE0 un serveur\
  \ web."
title: "Envoi d'une requ\xEAte HTTP"
weight: 44
---

## How to:
En Kotlin, utilisez la bibliothèque `ktor` pour simplifier les requêtes HTTP :

```kotlin
import io.ktor.client.*
import io.ktor.client.engine.cio.*
import io.ktor.client.request.*
import io.ktor.client.statement.*

suspend fun fetchUrl(url: String): HttpResponse {
    val client = HttpClient(CIO)
    val response: HttpResponse = client.get(url)
    client.close()
    return response
}

// Utilisez ça dans une coroutine, genre comme ça :
// val response = fetchUrl("http://example.com")
// println(response.readText())
```

Ce code va chercher le contenu de `http://example.com`. L'output ? Le HTML de la page.

## Deep Dive
Avant `ktor`, on avait pas mal d'autres choix en Kotlin, du genre Apache HttpClient ou OkHttp. Mais `ktor` est plus récent, conçu spécialement pour Kotlin et les coroutines. Cool, parce qu'il simplifie la vie avec sa gestion d'async.

Les requêtes HTTP sont au coeur du web depuis Tim Berners-Lee en a profité pour partager des docs au CERN dans les années 90. Maintenant, elles sont partout, pour tout et n'importe quoi touchant le web.

Le truc avec les requêtes HTTP, c'est de bien gérer le réseau. Ça peut être lent, ça peut foirer. Gérez les timeouts, les erreurs réseau, et assurez-vous de fermer les connexions.

## See Also
- Ktor docs pour plus de détails : [https://ktor.io/docs/](https://ktor.io/docs/)
- Kotlin coroutines guide, ça aide pour l'async : [https://kotlinlang.org/docs/coroutines-guide.html](https://kotlinlang.org/docs/coroutines-guide.html)
- Pour la comparaison, voici OkHttp : [https://square.github.io/okhttp/](https://square.github.io/okhttp/)
