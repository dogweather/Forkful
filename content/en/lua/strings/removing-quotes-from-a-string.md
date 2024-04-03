---
date: 2024-01-25 20:50:08.733239-07:00
description: "Stripping quotes from a string means peeling away those double or single\
  \ quote characters hugging your text. Coders do this to sanitize inputs, to ease\u2026"
lastmod: '2024-03-13T22:45:00.194427-06:00'
model: gpt-4-1106-preview
summary: Stripping quotes from a string means peeling away those double or single
  quote characters hugging your text.
title: Removing quotes from a string
weight: 9
---

## How to:
Here’s how to kick those quotes to the curb in Lua:

```lua
local function remove_quotes(str)
  return (str:gsub("^%p(.*)%p$", "%1"))
end

print(remove_quotes('"Hello, World!"'))     -- Hello, World!
print(remove_quotes("'Goodbye, Quotes!'"))  -- Goodbye, Quotes!
```

Bingo! Those quotes vanished like socks in a dryer.

## Deep Dive
Folks have been scrubbing quotes off strings since languages could handle text, which is pretty much forever. In Lua, the `gsub` function does the heavy lifting, wielding patterns like a scalpel to excise quotes. Alternatives? Sure, you could go regex in languages that support it, or write your own loop that chews through each character (yawn, but hey, it’s your time).

Lua's pattern matching gives you the oomph of regex-lite experience without importing a whole library. The caret (`^`) and dollar sign (`$`) match the start and end of the string, respectively; `%p` matches any punctuation character. After shaking off the leading and trailing punctuation, we capture everything else with `(.*),` and replace the whole match with that capture group using `" %1"`.

Do remember Lua’s pattern matching isn't as potent as full-blown regex engines – for example, it can't count or backtrack. This simplicity is both a blessing and a curse, depending on what quotes you’re wrangling and where they’re hiding.

## See Also
Plunge deeper into Lua’s pattern matching with the PiL (Programming in Lua) book: http://www.lua.org/pil/20.2.html

For sheer elegance, check out how other languages do it for comparison, starting with Python’s `str.strip`: https://docs.python.org/3/library/stdtypes.html#str.strip
