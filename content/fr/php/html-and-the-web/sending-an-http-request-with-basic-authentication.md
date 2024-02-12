---
title:                "Envoi d'une requête HTTP avec authentification de base"
date:                  2024-01-20T18:02:09.852088-07:00
model:                 gpt-4-1106-preview
simple_title:         "Envoi d'une requête HTTP avec authentification de base"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/php/sending-an-http-request-with-basic-authentication.md"
---

{{< edit_this_page >}}

## Quoi et pourquoi ?
Envoyer une requête HTTP avec authentification basique, c'est transmettre vos identifiants (username/password) en sécurisé pour accéder à une ressource. On le fait pour interagir avec des APIs ou des serveurs qui exigent une identification pour confirmer vos droits d'accès.

## Comment faire :
```PHP
<?php
$url = 'https://example.com/api/data';
$username = 'user';
$password = 'pass';

// Initialisation
$ch = curl_init($url);

// Authentification basique
curl_setopt($ch, CURLOPT_HTTPAUTH, CURLAUTH_BASIC);
curl_setopt($ch, CURLOPT_USERPWD, "$username:$password");

// Exécution de la requête
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$response = curl_exec($ch);
$status = curl_getinfo($ch, CURLINFO_HTTP_CODE);
curl_close($ch);

// Vérification de la réponse
if ($status == 200) {
    echo "Succès :\n";
    echo $response;
} else {
    echo "Erreur HTTP $status\n";
}
?>
```
Sortie:
```
Succès :
{"data":"informations confidentielles"}
```
## Plongée profonde :
Avant `cURL`, on utilisait `fsockopen()` ou des fonctions similaires pour créer des connexions réseau bas niveau. Aujourd'hui, `cURL` est répandu car il simplifie les requêtes HTTP.

Les alternatives à `cURL` incluent `file_get_contents()` avec un contexte de flux, ou même des bibliothèques comme `Guzzle`. Chaque méthode a ses propres avantages selon l'utilisation.

L'authentification basique n'est pas la plus sûre. Les identifiants sont codés en base64, ce qui n'est pas un cryptage. Utilisez HTTPS pour éviter l'exposition des données sensibles.

## Voir aussi :
- Documentation officielle de PHP cURL : https://www.php.net/manual/fr/book.curl.php
- RFC 7617 'The 'Basic' HTTP Authentication Scheme': https://tools.ietf.org/html/rfc7617
- Guzzle, un client HTTP PHP : http://docs.guzzlephp.org/en/stable/
