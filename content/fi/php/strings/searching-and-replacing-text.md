---
title:                "Tekstin etsiminen ja korvaaminen"
aliases:
- fi/php/searching-and-replacing-text.md
date:                  2024-01-20T17:58:45.203683-07:00
model:                 gpt-4-1106-preview
simple_title:         "Tekstin etsiminen ja korvaaminen"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/php/searching-and-replacing-text.md"
---

{{< edit_this_page >}}

## Mitä & Miksi?
Tekstin etsiminen ja korvaaminen on prosessi, jossa tekstistä löydettyjä osia vaihdetaan toisiin. Ohjelmoijat tarvitsevat tätä toimintaa datan siivoukseen, muotoilun muuttamiseen ja automatisoidakseen monotoniset editointitehtävät.

## How to:
PHP:ssa `str_replace`-funktio on yksi tapa tehdä tekstikorjauksia. Tässä yksinkertainen esimerkki:

```php
<?php
$originalString = "Hei maailma!";
$search = "maailma";
$replace = "kotikylä";
$result = str_replace($search, $replace, $originalString);

echo $result; // Tulostaa: Hei kotikylä!
?>
```

Ja jos halutaan suorittaa etsintä case-insensitive -tyyliin, käyttäisimme `str_ireplace`:

```php
<?php
$originalString = "Hei MAAILMA!";
$search = "maailma";
$replace = "kotikylä";
$result = str_ireplace($search, $replace, $originalString);

echo $result; // Tulostaa: Hei kotikylä!
?>
```

Regulaarilausekkeiden kanssa `preg_replace` on voimakas työkalu:

```php
<?php
$originalString = "Käyttäjä123";
$pattern = "/[0-9]+/";
$replace = "";
$result = preg_replace($pattern, $replace, $originalString);

echo $result; // Tulostaa: Käyttäjä
?>
```

## Deep Dive
Etsiminen ja korvaaminen ei ole uusi konsepti; se on ollut olennainen osa tekstieditoreita 1960-luvulta lähtien. PHP:n `str_replace` ja `str_ireplace` ovat helppokäyttöisiä perusfunktioita, jotka sopivat suurimpaan osaan yksinkertaisista etsi-ja-korvaa-tarpeista. `preg_replace` on joustavampi, mutta hitaampi, koska se käyttää säännöllisiä lausekkeita.

Eri tilanteet vaativat eri työkaluja. `str_replace` on nopea, kun tiedetään tarkalleen, mitä etsitään. Kun taas monimutkaisemmat tilanteet, kuten dynaamiset merkkijonot tai kuviot, vaativat `preg_replace`-joustavuutta.

PHP:n näiden funktioiden takana on C-ohjelmointikieli, jossa niitä implementoidaan. Tämä tarkoittaa, että suorituskyky on korkea, mutta myös, että käyttäjien on oltava tarkkana muistihuolien kanssa, kuten buffer overflow -riskejä välttäessään.

## See Also
Tutustu seuraaviin resursseihin, jos haluat syventää tietämystäsi:

- [PHP: str_replace - Manual](https://www.php.net/manual/en/function.str-replace.php)
- [PHP: str_ireplace - Manual](https://www.php.net/manual/en/function.str-ireplace.php)
- [PHP: preg_replace - Manual](https://www.php.net/manual/en/function.preg-replace.php)
- [Regular Expressions - PHP Manual](https://www.php.net/manual/en/book.pcre.php)
- [PHP String Functions - W3Schools](https://www.w3schools.com/php/php_ref_string.asp)
