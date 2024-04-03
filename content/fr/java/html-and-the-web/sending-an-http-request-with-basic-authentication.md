---
date: 2024-01-20 18:01:54.481972-07:00
description: "Envoyer une requ\xEAte HTTP avec une authentification de base, c'est\
  \ comme donner un mot de passe pour acc\xE9der \xE0 un site s\xE9curis\xE9. On fait\
  \ \xE7a pour prot\xE9ger\u2026"
lastmod: '2024-03-13T22:44:57.639741-06:00'
model: gpt-4-1106-preview
summary: "Envoyer une requ\xEAte HTTP avec une authentification de base, c'est comme\
  \ donner un mot de passe pour acc\xE9der \xE0 un site s\xE9curis\xE9."
title: "Envoi d'une requ\xEAte HTTP avec authentification de base"
weight: 45
---

## How to: (Comment faire :)
```java
import java.io.IOException;
import java.net.Authenticator;
import java.net.PasswordAuthentication;
import java.net.URL;
import javax.net.ssl.HttpsURLConnection;
import java.util.Base64;

public class HttpBasicAuth {
    
    public static void main(String[] args) throws IOException {
        String url = "https://example.com/api";
        String username = "user";
        String password = "pass";
        
        String auth = username + ":" + password;
        String encodedAuth = Base64.getEncoder().encodeToString(auth.getBytes());

        URL urlObject = new URL(url);
        HttpsURLConnection connection = (HttpsURLConnection) urlObject.openConnection();
        connection.setRequestProperty("Authorization", "Basic " + encodedAuth);

        int responseCode = connection.getResponseCode();
        System.out.println("Response Code: " + responseCode);
        // Handle input stream here to read the response
    }
}
```
Sortie attendue :
```
Response Code: 200
```
Si autre que 200, vérifiez les identifiants et l'URL.

## Deep Dive (Plongée en profondeur)
L'authentification de base HTTP existe depuis le début du web, introduite par le RFC 2617 en 1997, et maintenant définie par le RFC 7617. C'est simple mais pas super sécurisé en solo; on l'utilise souvent avec HTTPS pour plus de sécurité. Il y a des alternatives, comme l'authentification Digest ou des tokens, qui peuvent offrir une meilleure sécurité. En Java, on a plusieurs manières de les envoyer, comme montré, ou en utilisant des bibliothèques tierces comme Apache HttpClient ou OkHttp.

## See Also (Voir aussi)
- RFC 7617 pour les détails techniques : https://tools.ietf.org/html/rfc7617
- Apache HttpClient : https://hc.apache.org/httpcomponents-client-ga/
- OkHttp : https://square.github.io/okhttp/
