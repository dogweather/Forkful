---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:10:10.154747-07:00
description: "Il recupero della data corrente nella programmazione \xE8 un compito\
  \ cruciale per una moltitudine di applicazioni, inclusi i registri degli eventi,\
  \ la\u2026"
lastmod: '2024-03-13T22:44:43.567847-06:00'
model: gpt-4-0125-preview
summary: "Il recupero della data corrente nella programmazione \xE8 un compito cruciale\
  \ per una moltitudine di applicazioni, inclusi i registri degli eventi, la marcatura\
  \ temporale (timestamping) degli eventi o la pianificazione delle attivit\xE0."
title: Ottenere la data corrente
weight: 29
---

## Come fare:
Lua offre la funzione `os.date` per ottenere la data e l’ora correnti. La funzione può essere utilizzata senza argomenti per ottenere una stringa formattata o con specificatori di formato per personalizzare l'output. Ecco come usarla:

```lua
-- Ottenere la data e l'ora correnti come stringa formattata
print(os.date())  -- es., Thu Mar  3 14:02:03 2022

-- Personalizzare il formato dell'output
-- %Y per l'anno, %m per il mese, %d per il giorno, %H per l'ora, %M per i minuti
print(os.date("%Y-%m-%d %H:%M"))  -- es., 2022-03-03 14:02
```

Per manipolazioni più sofisticate di date e orari, Lua non dispone di librerie integrate tanto ricche quanto alcuni altri linguaggi di programmazione. Tuttavia, è possibile utilizzare librerie di terze parti come `lua-date` (https://github.com/Tieske/date). Questa libreria offre funzionalità più complete per la manipolazione di date e orari. Ecco come potresti usarla:

Prima, assicurati di avere installato la libreria `lua-date`. Tipicamente puoi installarla usando LuaRocks con il seguente comando:

```bash
luarocks install lua-date
```

Poi, puoi usarla nel tuo script Lua in questo modo:

```lua
local date = require("date")

-- Creare un oggetto data per la data e l'ora correnti
local now = date()

print(now:fmt("%Y-%m-%d %H:%M:%S"))  -- es., 2022-03-03 14:02:03
```

Questo esempio dimostra la creazione di un oggetto `date` che rappresenta il momento corrente, che poi puoi formattare in modo simile alla funzione `os.date` ma con flessibilità e opzioni aggiunte fornite dalla libreria `lua-date`.
