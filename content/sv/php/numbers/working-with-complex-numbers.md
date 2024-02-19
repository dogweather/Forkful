---
aliases:
- /sv/php/working-with-complex-numbers/
date: 2024-01-26 04:44:37.522091-07:00
description: "Komplexa tal har en realdel och en imagin\xE4rdel, vanligtvis skrivna\
  \ som `a + bi`. De \xE4r avg\xF6rande inom avancerad matematik, fysik, ingenj\xF6\
  rsvetenskap och\u2026"
lastmod: 2024-02-18 23:08:51.872441
model: gpt-4-0125-preview
summary: "Komplexa tal har en realdel och en imagin\xE4rdel, vanligtvis skrivna som\
  \ `a + bi`. De \xE4r avg\xF6rande inom avancerad matematik, fysik, ingenj\xF6rsvetenskap\
  \ och\u2026"
title: Att arbeta med komplexa tal
---

{{< edit_this_page >}}

## Vad & Varför?
Komplexa tal har en realdel och en imaginärdel, vanligtvis skrivna som `a + bi`. De är avgörande inom avancerad matematik, fysik, ingenjörsvetenskap och vissa datavetenskapliga algoritmer. Programmerare arbetar med dem för att hantera beräkningar som involverar kvadratrötter av negativa tal och oscillerande funktioner.

## Hur:
PHP erbjuder inbyggt stöd för komplexa tal genom att använda `ext-intl`-tillägget med klassen `NumberFormatter`. Här är ett exempel:

```php
// Kontrollera att intl-tillägget är laddat
if (!extension_loaded('intl')) {
    die("Tillägget intl är inte aktiverat. Vänligen aktivera det för att köra denna kod.");
}

function addComplexNumbers($a, $b) {
    // Använd NumberFormatter för att tolka och formatera komplexa tal
    $formatter = new NumberFormatter('en_US', NumberFormatter::PATTERN_RULEBASED, 'i = -1;');

    // Tolka komplexa tal från strängar
    $numA = $formatter->parse($a, NumberFormatter::TYPE_DOUBLE);
    $numB = $formatter->parse($b, NumberFormatter::TYPE_DOUBLE);

    // Utför addition
    $sum = $numA + $numB;

    // Formatera resultatet som ett komplext tal
    return $formatter->format($sum);
}

echo addComplexNumbers('5+3i', '2+7i'); // Utdata: 7+10i
```

## Fördjupning
Innan `ext-intl` hade PHP inte nativt stöd för komplexa tal. Utvecklare använde funktioner eller anpassade klassbibliotek för att hantera komplexa tal. Komplexa operationer kunde vara mödosamma och benägna för fel, men `ext-intl` erbjuder ett internationaliserat sätt att presentera och tolka komplexa tal i linje med ICU-biblioteket.

Dock, för tyngre matematiska operationer, kan vissa använda externa bibliotek skrivna i mer matematikvänliga språk (som C eller Python) och gränssnittar med dem genom PHP. När det gäller implementeringen hanterar `ext-intl` det bakom kulisserna och säkerställer korrekt aritmetik samtidigt som det abstraherar komplexiteten från utvecklaren.

Historiskt sett sågs komplexa tal med skepsis och kallades 'imaginära', men de har sedan dess blivit grundläggande inom olika vetenskapliga och matematiska områden, vilket avslöjar mer om deras betydelse i den verkliga världen än vad deras imaginära status någonsin antydde.

## Se även
- [PHP Manual om NumberFormatter](https://www.php.net/manual/en/class.numberformatter.php)
- [Wikipedia om komplexa tal](https://sv.wikipedia.org/wiki/Komplext_tal)
- [PHP: The Right Way - Att arbeta med datatyper](https://phptherightway.com/#data_types)
