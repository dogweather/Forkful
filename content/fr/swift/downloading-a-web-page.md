---
title:                "Téléchargement d'une page web"
date:                  2024-01-20T17:44:53.920698-07:00
model:                 gpt-4-1106-preview
simple_title:         "Téléchargement d'une page web"
programming_language: "Swift"
category:             "Swift"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/swift/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## What & Why?

Télécharger une page web, c'est récupérer son contenu via le réseau. Les programmeurs le font pour traiter des données, afficher des informations à l'utilisateur ou interagir avec des services web.

## How to:

Swift te permet de récupérer facilement le contenu d'une page web avec URLSession. Voici un exemple simple :

```Swift
import Foundation

let url = URL(string: "https://example.com")!
let task = URLSession.shared.dataTask(with: url) { data, response, error in
    if let error = error {
        print("Erreur lors du téléchargement : \(error)")
        return
    }

    if let data = data, let pageContent = String(data: data, encoding: .utf8) {
        print(pageContent)
    }
}

task.resume()

// Ne pas oublier que URLSession fonctionne en mode asynchrone !
// Pour un script ou une exécution en playground, utilisez RunLoop.main.run()
```

Exemple de sortie console:
```
<!doctype html>
<html>
<head>
    <title>Example Domain</title>
...
```

## Deep Dive:

Historiquement, en Swift, les programmeurs utilisaient souvent des bibliothèques comme Alamofire pour des opérations réseau. URLSession est l'outil moderne intégré par Apple désormais privilégié pour sa simplicité d'utilisation et son intégration système.

Il existe des alternatives à URLSession, comme Alamofire ou le framework Combine pour un style plus réactif. 

Pour bien comprendre la récupération d'une page web, on doit se pencher sur les détails d'implémentation tels que la gestion des erreurs, le décodage de la réponse et la prise en charge de la sécurité (comme le respect de TLS). La doc officielle d'Apple et les cours en ligne approfondissent ces sujets.

## See Also:

- La documentation officielle URLSession: [URLSession | Apple Developer Documentation](https://developer.apple.com/documentation/foundation/urlsession)
- Une introduction à Alamofire pour les alternatives: [Alamofire GitHub](https://github.com/Alamofire/Alamofire)
- Pour ceux qui s'intéressent au paradigme réactif: [Combine | Apple Developer Documentation](https://developer.apple.com/documentation/combine)