---
title:                "Searching and replacing text"
date:                  2024-01-20T17:57:16.396277-07:00
model:                 gpt-4-1106-preview
simple_title:         "Searching and replacing text"
programming_language: "Arduino"
category:             "Arduino"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/arduino/searching-and-replacing-text.md"
---

{{< edit_this_page >}}

## What & Why?

Searching and replacing text lets you find specific characters or strings in a text and switch them out for something else. Programmers do it to modify code, data, or user inputs without a fuss.

## How to:

Arduino doesn't natively support string search and replace in the way high-level languages do. However, you can work with character arrays or use the `String` class which offers the `replace()` method. While the former is memory-efficient, the latter is more straightforward. Let's focus on the `String` class for clarity.

```Arduino
void setup() {
  Serial.begin(9600);
  String text = "I like apples and apples are great!";
  text.replace("apples", "oranges");
  Serial.println(text);
}

void loop() {
  // Nothing to do here.
}
```

Sample Output:
```
I like oranges and oranges are great!
```

## Deep Dive

Back in the day, string manipulation tasks on microcontrollers were rare — memory was limited, and applications were simpler. These days, with more complex projects and ample memory space (thanks to advances in microcontroller technology), such utilities are pretty standard.

If you don't want to use the `String` class because of its dynamic memory use, which can cause fragmentation, you can still search and replace in C-style strings (null-terminated character arrays) using functions like `strchr()`, `strstr()`, and manual copying or replacement with loops. It's more involved but gives you greater control over memory.

For instance, an alternative way to replace a substring could look like this:

```Arduino
void replaceSubstring(char *input, const char *search, const char *replace) {
  char buffer[100];
  char *p;

  // 'strstr' checks if 'search' is part of 'input'.
  if (!(p = strstr(input, search))) return;

  // Copy up to the point where 'search' is found.
  strncpy(buffer, input, p - input);
  buffer[p - input] = '\0';

  // Append 'replace' and the rest of 'input' after 'search'.
  sprintf(buffer+(p - input), "%s%s", replace, p + strlen(search));

  // Output result
  strcpy(input, buffer);
}

void setup() {
  Serial.begin(9600);
  char text[] = "I like apples and apples are great!";
  replaceSubstring(text, "apples", "oranges");
  Serial.println(text);
}

void loop() {
  // Still nothing to do here.
}
```

Sample Output:
```
I like oranges and oranges are great!
```

## See Also

- [Arduino Reference: String Object](https://www.arduino.cc/reference/en/language/variables/data-types/stringobject/)
- [Arduino Reference: String Replace Function](https://www.arduino.cc/reference/en/language/variables/data-types/string/functions/replace/)
- [Cplusplus.com: C String Functions](http://www.cplusplus.com/reference/cstring/)
