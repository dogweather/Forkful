---
aliases:
- /en/fish-shell/reading-a-text-file/
date: 2024-01-20 17:54:14.326383-07:00
description: "Reading a text file is grabbing the data within a file for processing.\
  \ Programmers do it to extract information, configure apps, parse logs, or just\
  \ feed\u2026"
lastmod: 2024-02-18 23:09:11.498260
model: gpt-4-1106-preview
summary: "Reading a text file is grabbing the data within a file for processing. Programmers\
  \ do it to extract information, configure apps, parse logs, or just feed\u2026"
title: Reading a text file
---

{{< edit_this_page >}}

## What & Why?
Reading a text file is grabbing the data within a file for processing. Programmers do it to extract information, configure apps, parse logs, or just feed data into a script.

## How to:
Here's the Fish Shell scoop on opening those text files:

```Fish Shell
# Read a file line by line
while read -la line
    echo $line
end < file.txt
```

```Fish Shell
# Output contents of a file directly
cat file.txt
```

Sample output (from `cat`):

```plaintext
Hello, Fish!
Just swimming through files.
```

## Deep Dive
Once upon a time, even before Fish Shell made its debut circa 2005, reading files was a necessity. Unix shells have always had tools for this. Why Fish? It's friendly, it's modern, and it's sane with scripting defaults, making it a pleasant alternative to older shells.

The `while read` loop is handy for line-by-line tweaks. Don't forget that `read` has flags like `-la` for creating list variables from the line—great for comma-separated values.

On the flip side, `cat` is straightforward. It concatenates and displays file contents. It's been around in Unix since forever (well, 1971 to be exact).

In terms of performance, direct reads are generally faster and okay for smaller files. But when you've got a Moby Dick-sized text file, consider line-by-line processing or tools like `sed`, `awk`, or even `grep` if you're fishing for specific lines.

## See Also
- The [official Fish documentation](https://fishshell.com/docs/current/index.html) for a deep dive into all things Fish Shell.
- A [Unix StackExchange thread](https://unix.stackexchange.com/questions/tagged/fish) for broader community support and insights.
- A tutorial on [using awk in shell scripting](https://www.gnu.org/software/gawk/manual/gawk.html) might be handy if more complex text processing tasks come up.
