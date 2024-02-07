---
title:                "HTML:n jäsentäminen"
date:                  2024-02-01T21:58:02.752208-07:00
model:                 gpt-4-0125-preview
simple_title:         "HTML:n jäsentäminen"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/vba/parsing-html.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Mikä & Miksi?

HTML:n jäsentäminen Visual Basic for Applications (VBA) -ohjelmoinnissa tarkoittaa tiettyjen tietojen poimimista HTML-dokumentista. Ohjelmoijat tekevät sen automatisoidakseen web-sivujen lukemisen ja käsittelyn, kuten verkkosivuston sisällön skrapaamisen tai lomakkeiden automaattisen lähettämisen ja tiedonhaun, sovelluksissa, kuten Microsoft Excel tai Access, jotka tukevat VBA:ta.

## Kuinka:

VBA:ssa voit jäsentää HTML:ää käyttämällä `Microsoft HTML Object Library` -kirjastoa. Lisää viittaus tähän kirjastoon VBA-editorissasi siirtymällä kohtaan Työkalut > Viitteet ja valitsemalla `Microsoft HTML Object Library`. Tämä antaa sinulle pääsyn luokkiin HTML-dokumenttien navigointia ja manipulointia varten.

Tässä on yksinkertainen esimerkki, joka näyttää, miten voit ladata HTML-dokumentin tiedostosta ja poimia kaikki linkit (ankkuritagit):

```vb
Sub ParseHTML()
    Dim htmlDoc As MSHTML.HTMLDocument
    Dim htmlElement As MSHTML.IHTMLElement
    Dim htmlElements As MSHTML.IHTMLElementCollection
    Dim htmlFile As String
    Dim fileContent As String
    
    ' Lataa HTML-sisältö tiedostosta
    htmlFile = "C:\polku\tiedostoosi\file.html"
    Open htmlFile For Input As #1
    fileContent = Input$(LOF(1), 1)
    Close #1
    
    ' Alusta HTML-dokumentti
    Set htmlDoc = New MSHTML.HTMLDocument
    htmlDoc.body.innerHTML = fileContent
    
    ' Hanki kaikki ankkuritagit
    Set htmlElements = htmlDoc.getElementsByTagName("a")

    ' Käy läpi kaikki ankkurielementit ja tulosta href-attribuutti
    For Each htmlElement In htmlElements
        Debug.Print htmlElement.getAttribute("href")
    Next htmlElement
End Sub
```

Tämä skripti lukee HTML-tiedoston sisällön, lataa sen `HTMLDocument`-objektiin, hakee kaikki ankkurielementit (`<a>`-tagit) ja sitten iteroi niiden yli tulostaen kunkin `href`-attribuutin Välitön-ikkunaan.

## Syväsukellus:

Historiallisesti HTML:n jäsentäminen VBA:ssa on ollut hieman hankalaa modernien web-skrapaus- ja dokumentinhallintateknologioiden suoran tuen puutteen vuoksi. Microsoft HTML Object Library on tehokas, mutta jonkin verran vanhentunut ja ei ehkä käsittele moderneja web-standardeja yhtä sujuvasti kuin uudemmat teknologiat.

Monimutkaisiin HTML-jäsentämis- ja web-skrapaustehtäviin suositellaan usein vaihtoehtoisia työkaluja ja kieliä, kuten Pythonia kirjastoineen, kuten Beautiful Soup tai Scrapy. Nämä modernit työkalut tarjoavat enemmän joustavuutta, parempaa suorituskykyä ja ovat enemmän linjassa nykyisten web-standardien kanssa. Kuitenkin, työskenneltäessä Microsoft Officen ekosysteemissä, VBA:n käyttäminen Microsoft HTML Object Libraryn kanssa on arvokas taito. Se mahdollistaa suoran HTML-sisällön manipuloinnin tavalla, joka integroituu saumattomasti sovelluksiin, kuten Excel ja Access, tarjoten suoraviivaisen menetelmän tehtävien suorittamiseen, jotka koskevat perus HTML-dokumenttien käsittelyä tarvitsematta poistua tutusta VBA-ympäristöstä.
