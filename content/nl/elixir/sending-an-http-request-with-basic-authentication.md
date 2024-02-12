---
title:                "Een HTTP-verzoek verzenden met basisauthenticatie"
aliases:
- nl/elixir/sending-an-http-request-with-basic-authentication.md
date:                  2024-01-28T22:08:09.928779-07:00
model:                 gpt-4-0125-preview
simple_title:         "Een HTTP-verzoek verzenden met basisauthenticatie"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/elixir/sending-an-http-request-with-basic-authentication.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?

Het verzenden van een HTTP-verzoek met basisauthenticatie houdt in dat je een gebruikersnaam en wachtwoord toevoegt aan je verzoek om toegang te krijgen tot een beveiligde bron. Programmeurs doen dit om veilige toegang tot en overdracht van gegevens te garanderen, en onbevoegde gebruikers buiten te houden.

## Hoe te:

Om een HTTP-verzoek met basisauthenticatie in Elixir te versturen, kun je de `HTTPoison` bibliotheek gebruiken:

```elixir
# Voeg HTTPoison toe aan de afhankelijkheden van je project in mix.exs
defp deps do
  [
    {:httpoison, "~> 1.8"}
  ]
end

# Laten we nu een verzoek maken met basisauth

# Voer `mix deps.get` uit om de afhankelijkheid op te halen

# In je Elixir-code
defmodule BasicAuthRequest do
  def send_request do
    # Codeer inloggegevens "gebruikersnaam:wachtwoord" met Base64
    basic_auth =
      "gebruikersnaam:wachtwoord"
      |> Base.encode64()

    # Stel de Authorization-header in
    headers = [{"Authorization", "Basic #{basic_auth}"}]

    # Doe een GET-verzoek naar https://example.com/protected-resource
    HTTPoison.get("https://example.com/protected-resource", headers)
  end
end

# Roep de functie aan
{:ok, response} = BasicAuthRequest.send_request()
IO.inspect(response.status_code)  # Zou 200 moeten zijn als de authenticatie succesvol is
```

Als de basisauthenticatie succesvol is, krijg je een `200` statuscode. Mislukte authenticatie resulteert doorgaans in een `401`.

## Diepgaand

Basisauthenticatie is een deel van HTTP gedefinieerd in RFC 7617, daterend uit de vroege dagen van het web. Het is eenvoudig maar minder veilig dan moderne methoden, aangezien inloggegevens bij elke aanvraag worden verzonden (base64 gecodeerd, niet versleuteld).

Alternatieven zijn onder meer:
- OAuth: Een open standaard voor toegangsdelegatie, gebruikt om websites of applicaties toegang te verlenen tot hun informatie op andere websites zonder hen de wachtwoorden te geven.
- API-sleutels: Unieke identificatoren gebruikt om een gebruiker of een programma te authenticeren in API-verzoeken.
- Bearer Tokens/JWT: Beveiligingstokens die alle gebruikersgegevens bevatten die nodig zijn om de gebruiker te authenticeren.

Wat betreft implementatie, wanneer we `HTTPoison` gebruiken, wij:
- Codeer de gebruikersnaam en het wachtwoord in Base64;
- Voeg deze gecodeerde string toe aan de `Authorization` header voorafgegaan door "Basic ";
- Verzend het verzoek aan de server in de hoop dat toegang wordt verleend.

Onthoud, basisauth is in klare tekst en kan gemakkelijk worden gedecodeerd. Het is alleen veilig over HTTPS.

## Zie Ook

- HTTPoison documentatie: https://hexdocs.pm/httpoison
- Schema voor basisauthenticatie (RFC 7617): https://tools.ietf.org/html/rfc7617
- Documentatie van Elixir's `Base` module: https://hexdocs.pm/elixir/Base.html
- OAuth 2.0 Autorisatie Framework: https://oauth.net/2/
