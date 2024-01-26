---
title:                "Å sende en HTTP-forespørsel med grunnleggende autentisering"
date:                  2024-01-20T18:02:04.042473-07:00
model:                 gpt-4-1106-preview
simple_title:         "Å sende en HTTP-forespørsel med grunnleggende autentisering"
programming_language: "Java"
category:             "Java"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/java/sending-an-http-request-with-basic-authentication.md"
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Å sende en HTTP-forespørsel med grunnleggende autentisering betyr å inkludere brukernavn og passord for tilgangskontroll. Programmerere gjør dette for å sikre at API-forespørsler er autoriserte.

## Slik gjør du:
```java
import java.net.URI;
import java.net.http.HttpClient;
import java.net.http.HttpRequest;
import java.net.http.HttpResponse;
import java.util.Base64;

public class BasicAuthExample {
    public static void main(String[] args) {
        String url = "https://example.com/api";
        String username = "brukernavn";
        String password = "passord";
        
        String encodedCredentials = Base64.getEncoder().encodeToString((username + ":" + password).getBytes());
        String authorizationHeader = "Basic " + encodedCredentials;
        
        HttpClient client = HttpClient.newHttpClient();
        HttpRequest request = HttpRequest.newBuilder()
                .uri(URI.create(url))
                .header("Authorization", authorizationHeader)
                .build();
                
        try {
            HttpResponse<String> response = client.send(request, HttpResponse.BodyHandlers.ofString());
            System.out.println("Statuskode: " + response.statusCode());
            System.out.println("Respons: " + response.body());
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```
Sample output:
```
Statuskode: 200
Respons: { "message": "Innlogget!" }
```

## Dypdykk
Basic autentisering er en gammel metode, del av HTTP-standarden siden 1990-tallet. Den passer enkle scenarier men er ikke den sikreste, fordi brukernavn og passord er kodet, ikke kryptert. Alternativer inkluderer OAuth, tokens og API-nøkler. I Java, bruk `java.net.http.HttpClient` for å lage HTTP-forespørsler. Du må kode brukernavn og passord med Base64. Sørg alltid for å bruke HTTPS for å beskytte legitimasjonen under overføring.

## Se også
- [HTTP Authentication: Basic and Digest Access Authentication](https://tools.ietf.org/html/rfc2617)
- [Java SE Documentation for java.net.http](https://docs.oracle.com/en/java/javase/15/docs/api/java.net.http/java/net/http/package-summary.html)
- [Understanding Base64 Encoding in Java](https://www.baeldung.com/java-base64-encode-and-decode)
