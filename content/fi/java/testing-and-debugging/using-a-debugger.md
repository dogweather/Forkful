---
title:                "Debuggerin käyttö"
aliases:
- fi/java/using-a-debugger.md
date:                  2024-01-26T03:49:42.390443-07:00
model:                 gpt-4-0125-preview
simple_title:         "Debuggerin käyttö"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/java/using-a-debugger.md"
---

{{< edit_this_page >}}

## Mikä & Miksi?
Debuggerin käyttäminen tarkoittaa työkalun käyttöä koodisi testaamiseen ja virheiden korjaamiseen. Ohjelmoijat tekevät näin ymmärtääkseen sovellustensa virtauksen, paikantaakseen virheiden lähteet ja varmistaakseen suorituksenalaisen logiikan.

## Miten:
Oletetaan, että sinulla on yksinkertainen Java-ohjelma, joka temppuilee, etkä voi keksiä miksi. Tässä on, miten käynnistäisit debuggerin käyttämällä Eclipseä, joka on yksi suosituimmista IDEistä Java-kehityksessä:

Ensiksi varmista, että olet asettanut katkaisukohdan. Sitten, napsauta tiedostoa oikealla hiiren painikkeella, valitse 'Debug As', ja klikkaa 'Java Application'.

```Java
public class DebugExample {
    public static void main(String[] args) {
        int a = 5;
        int b = 0;
        // Aseta katkaisukohta tähän
        int tulos = divide(a, b);
        System.out.println("Tulos on: " + tulos);
    }

    private static int divide(int jaettava, int jakaja) {
        // Toinen hyvä paikka katkaisukohdalle
        return jaettava / jakaja;
    }
}
```

Tämän seurauksena ohjelmasi pysähtyy katkaisukohtaan, ja voit tutkia muuttujia, käydä läpi koodia rivi riviltä ja tarkkailla, kuinka ohjelmasi käyttäytyy.

Esimerkki tulosteesta (debuggerin konsolissa):
```
Katkaisukohta osui rivillä: int tulos = divide(a, b);
```

## Syväsukellus
Debuggauksen käsite on ollut olemassa ohjelmoinnin alkuaikoina. Tarinan mukaan termi "bug" (suom. vika) tuli todellisesta, tietokoneen sisältä löydetystä koiperhosen toukasta, jonka löysi Grace Hopper, alansa pioneeri. Ajan kuluessa olemme saaneet käyttöömme kehittyneitä IDEitä kuten IntelliJ IDEA, Eclipse ja NetBeans, jotka sisältävät tehokkaita debuggereita.

IDE-debuggereiden vaihtoehtoja ovat lokitiedostot, tulostuslauseet (köyhän miehen debuggeri), väitteet ja itsenäiset debuggaustyökalut kuten jdb (Java Debugger), joka on osa Java Development Kit (JDK):ta.

Debuggeri toimii antamalla ohjelmoijan keskeyttää suorituksen (katkaisukohdat), käydä läpi koodia, tarkastella muuttujien arvoja, muuttaa noita arvoja lennossa ja jopa suorittaa koodilohkoja lohko kerrallaan. Debuggerin käyttämistä pidetään usein korvaamattomana tekniikkana monimutkaisten sovellusten kehittämisessä, jossa tarkan koodirivin löytäminen, joka aiheuttaa ongelman, voidaan rinnastaa neulan etsimiseen heinäsuovasta.

## Katso myös
- Virallinen Oraclen dokumentaatio debuggauksesta: [Oracle Java SE Debugging](https://docs.oracle.com/javase/8/docs/technotes/tools/windows/jdb.html)
- Eclipsen opas debuggaukseen: [Eclipse Debugging Tips](https://www.eclipse.org/community/eclipse_newsletter/2017/june/article4.php)
- VisualVM, visuaalinen työkalu, joka integroi useita komentorivin JDK-työkaluja ja kevyitä profilointimahdollisuuksia: [VisualVM](https://visualvm.github.io/)
