---
title:                "Reading command line arguments"
date:                  2024-01-20T17:55:41.331480-07:00
model:                 gpt-4-1106-preview
simple_title:         "Reading command line arguments"
programming_language: "Clojure"
category:             "Clojure"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/clojure/reading-command-line-arguments.md"
---

{{< edit_this_page >}}

## What & Why?

Reading command line arguments lets a program grab info straight from the user's terminal command. Programmers do it to customize a program's behavior without changing the code itself.

## How to:

In Clojure, you snag command line arguments with `*command-line-args*`. Here's a simple example:

```clojure
;; Assume this code is in a file called `echo.clj`

(defn -main [& args]
  (println "You've entered:" args))

;; To run: `clojure echo.clj arg1 arg2 arg3`
```

Sample output:

```
You've entered: (arg1 arg2 arg3)
```

Need to process them? Use Clojure's collection functions.

```clojure
(defn -main [& args]
  (let [processed-args (mapv str/upper-case args)]
    (println "Upper-cased:" processed-args)))

;; Now, running `clojure echo.clj hello world` will output:
```

Sample output:

```
Upper-cased: ["HELLO" "WORLD"]
```

## Deep Dive

The `*command-line-args*` is a var in Clojure, set to a sequence of arguments passed to the script. It's been around since Clojure's early days, showing Clojure treats command line args as first-class citizens.

Alternatives? Java's mechanisms for grabbing command line args work in Clojure, too, thanks to interoperability. But that's more verbose.

As for implementation details, when Clojure starts, it parses the args and stores them in `*command-line-args*`. Your script can then do whatever with them—parse, ignore, transform, you name it.

## See Also

- Official Clojure CLI tools: https://clojure.org/guides/deps_and_cli
- Clojure from the ground up: Command-line scripting: https://aphyr.com/posts/305-clojure-from-the-ground-up-command-line
- ClojureDocs on *command-line-args*: https://clojuredocs.org/clojure.core/*command-line-args*
