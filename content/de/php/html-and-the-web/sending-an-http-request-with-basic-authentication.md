---
date: 2024-01-20 18:02:26.257898-07:00
description: "Das Senden einer HTTP-Anfrage mit Basisauthentifizierung bedeutet, dass\
  \ wir unseren Nutzernamen und unser Passwort im Klartext (base64-kodiert) \xFCber\
  \ das\u2026"
lastmod: '2024-03-13T22:44:53.971969-06:00'
model: gpt-4-1106-preview
summary: "Das Senden einer HTTP-Anfrage mit Basisauthentifizierung bedeutet, dass\
  \ wir unseren Nutzernamen und unser Passwort im Klartext (base64-kodiert) \xFCber\
  \ das Netzwerk senden, um uns gegen\xFCber dem Server zu authentifizieren."
title: HTTP-Anfragen mit Basisauthentifizierung senden
weight: 45
---

## So geht's:
```php
<?php
$url = 'https://beispiel-api.de/daten';
$benutzername = 'DeinBenutzer';
$passwort = 'DeinPasswort';

$context = stream_context_create([
    'http' => [
        'header' => 'Authorization: Basic ' . base64_encode("$benutzername:$passwort"),
    ],
]);

$result = file_get_contents($url, false, $context);

if ($result !== false) {
    echo "Erfolg: " . $result;
} else {
    echo "Fehler beim Abrufen der Daten.";
}
?>
```

Beispiel-Ausgabe:
```
Erfolg: {"nachricht": "Hallo, Welt!"}
```

## Tiefgang
Die Basisauthentifizierung ist ein altbewährtes Verfahren aus den Anfangstagen des Internets und gehört zum HTTP-Standard. Es gibt sicherere Methoden, wie OAuth, aber Basisauthentifizierung bleibt populär wegen ihrer Einfachheit und breiten Unterstützung. Wichtig zu betonen ist, dass sie nur über HTTPS genutzt werden sollte, um die Zugangsdaten zu verschlüsseln.

Alternativen wie API-Schlüssel, Token-basierte Authentifizierung oder OAuth bieten je nach Anforderung und Risikostufe mehr Sicherheit und Flexibilität. Die Implementierung der Basisauthentifizierung in PHP kann über cURL oder Stream-Kontexte (wie im Beispiel oben) erfolgen. Beachte, dass `file_get_contents` und Kontext-Streams in manchen Hosting-Umgebungen eingeschränkt sein können.

## Siehe auch
- PHP Manual über HTTP Authentifizierung: https://www.php.net/manual/de/features.http-auth.php
- cURL-Dokumentation für fortgeschrittene Authentifizierungsmethoden: https://www.php.net/manual/de/book.curl.php
- Sicherheitsüberlegungen bei Basisauthentifizierung: https://owasp.org/www-community/controls/Basic_Authentication
- Anleitung zu sichereren Authentifizierungsmethoden: https://auth0.com/docs/authentication
