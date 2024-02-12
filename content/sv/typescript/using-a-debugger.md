---
title:                "Att använda en debugger"
aliases:
- sv/typescript/using-a-debugger.md
date:                  2024-01-26T04:11:20.937214-07:00
model:                 gpt-4-0125-preview
simple_title:         "Att använda en debugger"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/typescript/using-a-debugger.md"
---

{{< edit_this_page >}}

## Vad & Varför?
En debugger är ett verktyg som låter dig undersöka och ändra det inre arbetet i din kod medan den körs. Programmerare använder den för att krossa buggar genom att stega igenom sin kod, inspektera variabler och förstå flödet i sitt program.

## Hur man gör:

För att komma igång med en debugger i TypeScript behöver du bara en stödd IDE (som Visual Studio Code) och en `launch.json`-konfiguration. Här är ett snabbt exempel för en Node.js-applikation:

```TypeScript
// app.ts
function greet(name: string) {
    console.log(`Hej, ${name}!`);
}

const userName = 'Ada';
greet(userName);
```

För att felsöka detta skapar du en `launch.json`-fil under `.vscode`-mappen:

```JSON
{
    "version": "0.2.0",
    "configurations": [
        {
            "type": "node",
            "request": "launch",
            "name": "Starta program",
            "skipFiles": ["<node_internals>/**"],
            "program": "${workspaceFolder}/app.ts",
            "preLaunchTask": "tsc: bygg - tsconfig.json",
            "outFiles": ["${workspaceFolder}/build/**/*.js"]
        }
    ]
}
```

Sedan anger du en brytpunkt i din `greet`-funktion genom att klicka på vänster sida om radnumret i din IDE. Tryck F5 för att starta felsökning och se din app pausa vid brytpunkten. Du kan nu hovra över variabler, övervaka uttryck och stega igenom din kod med lätthet.

## Fördjupning

Förr i tiden, innan integrerade utvecklingsmiljöer (IDEs) blev slipade, gjordes felsökning ofta med utskriftsutlåtanden (a.k.a `console.log` felsökning). Det fungerade, på sätt och vis, men det var som att försöka hitta en nål i en höstack med ögonbindel.

Moderna debuggers är som en schweizisk armékniv för felsökning. Med utvecklingen av TypeScript och Node.js finns det olika debugger tillgängliga, från den inbyggda Node.js-inspektören till webbläsarutvecklarverktyg för klientsidan felsökning.

Node.js-inspektören fungerar genom att fästa vid din körande applikation; den kommunicerar över Chrome DevTools-protokollet, vilket gör din Chrome-webbläsare till en kraftfull felsökningskonsol. Denna integration möjliggör en visuellt interaktiv och detaljerad felsökningsession, jämfört med traditionella felsökningstekniker via kommandoraden.

## Se också

För lite extra läsning och några pro-tips, kolla in:

- [TypeScript Debugging i Visual Studio Code](https://code.visualstudio.com/docs/typescript/typescript-debugging)
- [Node.js Felsökningsguide](https://nodejs.org/en/docs/guides/debugging-getting-started/)
- [Chrome DevTools Dokumentation](https://developers.google.com/web/tools/chrome-devtools)
