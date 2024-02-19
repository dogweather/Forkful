---
aliases:
- /fi/java/sending-an-http-request/
date: 2024-01-20 17:59:58.354885-07:00
description: "L\xE4hett\xE4m\xE4ll\xE4 HTTP-pyynn\xF6n, ohjelmat voivat pyyt\xE4\xE4\
  \ tietoa tai l\xE4hett\xE4\xE4 dataa web-palvelimelle. Ohjelmoijat tekev\xE4t sen,\
  \ koska se on netin kanssak\xE4ymisen\u2026"
lastmod: 2024-02-18 23:09:07.454799
model: gpt-4-1106-preview
summary: "L\xE4hett\xE4m\xE4ll\xE4 HTTP-pyynn\xF6n, ohjelmat voivat pyyt\xE4\xE4 tietoa\
  \ tai l\xE4hett\xE4\xE4 dataa web-palvelimelle. Ohjelmoijat tekev\xE4t sen, koska\
  \ se on netin kanssak\xE4ymisen\u2026"
title: "HTTP-pyynn\xF6n l\xE4hett\xE4minen"
---

{{< edit_this_page >}}

## What & Why? (Mikä ja Miksi?)
Lähettämällä HTTP-pyynnön, ohjelmat voivat pyytää tietoa tai lähettää dataa web-palvelimelle. Ohjelmoijat tekevät sen, koska se on netin kanssakäymisen ydin - ilman pyyntöjä, ei keskustelua palvelimien kanssa.

## How to: (Kuinka tehdä:)
Java tarjoaa `java.net.http`-paketin HTTP-pyyntöjen lähettämiseen, joka sisältää `HttpClient`, `HttpRequest` ja `HttpResponse` -luokat.

```Java
import java.net.URI;
import java.net.http.HttpClient;
import java.net.http.HttpRequest;
import java.net.http.HttpResponse;
import java.io.IOException;
import java.util.concurrent.ExecutionException;

public class HttpExample {
    public static void main(String[] args) throws IOException, InterruptedException, ExecutionException {
        HttpClient client = HttpClient.newHttpClient();

        HttpRequest request = HttpRequest.newBuilder()
                .uri(URI.create("https://www.example.com"))
                .GET() // Voi olla GET, POST, PUT, DELETE jne.
                .build();

        HttpResponse<String> response = client.send(request, HttpResponse.BodyHandlers.ofString());

        System.out.println("Status Code: " + response.statusCode());
        System.out.println("Response Body:\n" + response.body());
    }
}
```

Tuloste voi näyttää esimerkiksi tältä:
```
Status Code: 200
Response Body:
<!doctype html>...
```

## Deep Dive (Sukellus syvemmälle):
Ennen `java.net.http`-pakettia, ohjelmoijat käyttivät `HttpURLConnection`-luokkaa tai ulkopuolisia kirjastoja, kuten Apache HttpClient. `java.net.http` esiteltiin vasta Java 11:ssä, ja se teki HTTP-pyyntöjen käsittelystä yksinkertaisempaa ja modernimpaa.

HTTP-pyyntöjä voidaan lähettää synkronisesti tai asynkronisesti. Edellä oleva esimerkki käyttää synkronista tapaa, joka odottaa ja palauttaa vastauksen välittömästi. Asynkroninen lähetys käyttää `CompletableFuture`-objektia ja antaa ohjelman jatkaa muiden tehtävien suorittamista, kunnes vastaus palautuu.

Eri HTTP-metodit palvelevat eri tarkoituksia. `GET` pyytää dataa, `POST` lähettää uutta dataa, `PUT` päivittää olemassaolevaa dataa ja `DELETE` poistaa sitä. Oikean metodin valinta perustuu siihen, mitä halutaan tehdä.

## See Also (Katso myös):
- [Oracle's HttpRequest docs](https://docs.oracle.com/en/java/javase/17/docs/api/java.net.http/java/net/http/HttpRequest.html)
- [Java 11 HttpClient Tutorial](https://openjdk.java.net/groups/net/httpclient/intro.html)
- [Maven Repository for Apache HttpClient](https://mvnrepository.com/artifact/org.apache.httpcomponents/httpclient)
