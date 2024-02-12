---
title:                "HTTP-pyynnön lähettäminen perusautentikoinnilla"
aliases:
- fi/elixir/sending-an-http-request-with-basic-authentication.md
date:                  2024-01-20T18:01:30.586517-07:00
model:                 gpt-4-1106-preview
simple_title:         "HTTP-pyynnön lähettäminen perusautentikoinnilla"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/elixir/sending-an-http-request-with-basic-authentication.md"
---

{{< edit_this_page >}}

## What & Why?
HTTP-pyyntö perusautentikaatiolla on web-palvelimelle lähetetty pyyntö, jossa on käyttäjätunnus ja salasana. Koodarit käyttävät tätä yksinkertaiseen pääsynvalvontaan, kun haluavat suojata resurssejaan.

## How to:
Lähettääksesi HTTP-pyynnön Elixirissä perusautentikaatiolla, voit käyttää `HTTPoison`-kirjastoa. Tässä on pikainen esimerkki:

```elixir
# Add HTTPoison to your mix.exs dependencies if you haven't already:
# {:httpoison, "~> 1.8"}

defmodule BasicAuthExample do
  def send_request do
    auth = encode_credentials("user", "pass")
    HTTPoison.get("http://example.com", [], basic_auth: auth)
  end

  defp encode_credentials(username, password) do
    Base.encode64("#{username}:#{password}")
  end
end

# Call the function and get the response
{:ok, response} = BasicAuthExample.send_request()
```

Tämän pitäisi antaa sinulle vastaus, kuten:

```elixir
{:ok,
 %HTTPoison.Response{
   body: "Response body here...",
   status_code: 200,
   ...
 }}
```

## Deep Dive
Perusautentikaatio on HTTP-protokollan vanhin autentikointitapa. Se on suoraviivainen, mutta ei kauhean turvallinen, koska käyttäjätunnus ja salasana lähetetään koodattuna, mutta ei salattuna. Siksi käytä sitä vain HTTPS-protokollan yli.

Elixirissä `HTTPoison` on suosittu HTTP-asiakaskirjasto. Se tarjoaa yksinkertaisen tavan tehdä pyyntöjä ja käsittää vastauksia. Vaihtoehtona on `Tesla`, joka on joustavampi ja modulaarisempi asiakaskirjasto.

Implementaation yksityiskohdista, lähetät `Authorization`-otsakkeen, joka sisältää `'Basic '`, ja perään Base64-koodatun merkkijonon `'käyttäjätunnus:salasana'`. Serveri dekoodaa ja tarkistaa tämän ennen resurssin paljastamista. 

## See Also
- [HTTPoison GitHub](https://github.com/edgurgel/httpoison)
- [Tesla GitHub](https://github.com/teamon/tesla)
- [Elixir Base module](https://hexdocs.pm/elixir/Base.html)
- [Basic authentication on MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication#basic_authentication_scheme)
