---
title:                "Handling errors"
aliases:
- /en/fish-shell/handling-errors/
date:                  2024-01-21T21:19:23.845730-07:00
model:                 gpt-4-1106-preview
simple_title:         "Handling errors"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/fish-shell/handling-errors.md"
---

{{< edit_this_page >}}

## What & Why?
Error handling lets your script deal with the unexpected gracefully. We do it to manage failure without turning our user's hair gray.

## How to:
To catch errors in Fish, lean on the `status` command and conditionals. Say `ping` fails; here's how to detect that:

```fish
ping -c 1 example.com
if not status is-success
    echo "Something fishy happened with the ping."
end
```

Sample output if `ping` fails:

```
Something fishy happened with the ping.
```

To handle a specific error code, use `status --is`:

```fish
false
if status --is 1
    echo "Caught an error with code 1."
end
```

Sample output:
```
Caught an error with code 1.
```

For a more robust approach, consider using a function:

```fish
function try_ping
    ping -c 1 example.com
    or begin
        echo "Ping failed with status $status"
        return 1
    end
end

try_ping
```

## Deep Dive
Error handling in Fish doesn't match the `try/catch` paradigm you might know from higher-level languages. Instead, you have straightforward exit statuses provided by the `status` command.

Historically, in Unix-like systems, an exit status of `0` means success, while any non-zero value indicates an error, which commonly reflects different failure reasons. This convention is employed by most command-line utilities and hence, by Fish iteself.

Alternatives to `status` checks in Fish include signal handling via `trap` in other shells, but Fish prefers more explicit status checking, because it's cleaner and less prone to side effects.

Implementation-wise, error handling in Fish remains simple yet powerful, largely due to its non-blocking nature and emphasis on clear syntax, as shown in the examples. Error codes blend nicely with functions, allowing for modular and readable error management.

## See Also
- Fish documentation on conditionals: https://fishshell.com/docs/current/language.html#conditionals
- Fish tutorial on error handling: https://fishshell.com/docs/current/tutorial.html#error-handling
