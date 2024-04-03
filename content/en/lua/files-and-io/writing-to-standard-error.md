---
date: 2024-02-03 19:03:31.575552-07:00
description: "Writing to standard error (stderr) is about directing error messages\
  \ and diagnostic outputs to a separate channel, distinct from standard output (stdout).\u2026"
lastmod: '2024-03-13T22:45:00.220305-06:00'
model: gpt-4-0125-preview
summary: Writing to standard error (stderr) is about directing error messages and
  diagnostic outputs to a separate channel, distinct from standard output (stdout).
title: Writing to standard error
weight: 25
---

## How to:
In Lua, writing to stderr can be achieved using the `io.stderr:write()` function. Here's how you can write a simple error message to standard error:

```lua
io.stderr:write("Error: Invalid input.\n")
```

Should you need to output a variable or combine multiple pieces of data, concatenate them within the write function:

```lua
local errorMessage = "Invalid input."
io.stderr:write("Error: " .. errorMessage .. "\n")
```

**Sample Output on stderr:**
```
Error: Invalid input.
```

For more complex scenarios, or when working with larger applications, you might consider third-party logging libraries such as LuaLogging. With LuaLogging, you can direct logs to different destinations, including stderr. Here's a brief example:

First, ensure LuaLogging is installed using LuaRocks:

```
luarocks install lualogging
```

Then, to write an error message to stderr using LuaLogging:

```lua
local logging = require("logging")
local logger = logging.stderr()
logger:error("Error: Invalid input.")
```

This approach offers the advantage of standardized logging across your application, with the added flexibility of setting log levels (e.g., ERROR, WARN, INFO) through a simple API.
