---
date: 2024-01-20 15:32:28.787617-07:00
description: "HTML-tiedostojen j\xE4sent\xE4minen eli parsing tarkoittaa HTML-koodin\
  \ muuttamista rakenteelliseksi tiedoksi, mit\xE4 ohjelma voi k\xE4ytt\xE4\xE4 hy\xF6\
  dyksi. Koodaajat\u2026"
lastmod: '2024-03-13T22:44:56.528422-06:00'
model: unknown
summary: "HTML-tiedostojen j\xE4sent\xE4minen eli parsing tarkoittaa HTML-koodin muuttamista\
  \ rakenteelliseksi tiedoksi, mit\xE4 ohjelma voi k\xE4ytt\xE4\xE4 hy\xF6dyksi."
title: "HTML:n j\xE4sent\xE4minen"
weight: 43
---

## How to:
Kotlin-kehittäjät käyttävät usein jsoup-kirjastoa HTML-dokumenttien jäsentämiseen. Alla on yksinkertainen esimerkki:

```Kotlin
import org.jsoup.Jsoup

fun main() {
    val html = "<html><head><title>Otsikko</title></head><body><p>Hei maailma!</p></body></html>"
    val doc = Jsoup.parse(html)
    
    val title = doc.title()
    val bodyText = doc.body().text()

    println("Otsikko: $title")
    println("Leipäteksti: $bodyText")
}
```
Tuloste:
```
Otsikko: Otsikko
Leipäteksti: Hei maailma!
```

## Deep Dive
HTML-jäsentämisen tarpeellisuus nousi 1990-luvulla, kun internet alkoi yleistyä. Historiallisesti jäsentäminen on ollut hankalaa kielen löyhän syntaksin vuoksi. Nykyään kirjastoja kuten jsoup on kehitetty helpottamaan prosessia ja parantamaan luotettavuutta.

Vaihtoehtoja jsoupille ovat esimerkiksi HtmlCleaner ja Jericho HTML Parser. Nämä kirjastot eroavat toisistaan niin suorituskyvyn, joustavuuden kuin API:nkin osalta.

Jäsennettäessä HTML:ää on tärkeää muistaa dokumentin rakennetta koskevat oletukset. Esimerkiksi jsoup käsittelee HTML-dokumentit käyttäen DOM-mallia (Document Object Model), joka muuntaa dokkarin puurakenteeksi (node tree).

## See Also
- jsoup: Java HTML Parser: https://jsoup.org
- HtmlCleaner Project: http://htmlcleaner.sourceforge.net 
- Jericho HTML Parser: http://jericho.htmlparser.net/docs/index.html
- W3C's HTML parser comparison: https://www.w3.org/html/wg/drafts/html/master/single-page.html#parsing
