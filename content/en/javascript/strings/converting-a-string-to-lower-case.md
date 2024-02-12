---
title:                "Converting a string to lower case"
aliases:
- /en/javascript/converting-a-string-to-lower-case/
date:                  2024-01-20T17:38:31.875730-07:00
model:                 gpt-4-1106-preview
simple_title:         "Converting a string to lower case"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/javascript/converting-a-string-to-lower-case.md"
---

{{< edit_this_page >}}

## What & Why?
Converting a string to lowercase means transforming all the characters within it to their lower case counterparts. Programmers do it for consistency, especially for case-insensitive comparisons, like when normalizing user input or searching text content.

## How to:
In JavaScript, we convert a string to lowercase with the `.toLowerCase()` method. It's as simple as:

```javascript
let greeting = "Hello, World!";
let lowerCaseGreeting = greeting.toLowerCase();
console.log(lowerCaseGreeting); // "hello, world!"
```

When used, each character in the original string is converted, if possible, to lowercase:

```javascript
let mixedCase = "jAvAScript ROCKs!";
let lowerCased = mixedCase.toLowerCase();
console.log(lowerCased); // "javascript rocks!"
```

Note that characters which have no lowercase equivalents remain unchanged.

## Deep Dive
In the old days, handling text meant being wary of character encodings and manual conversions. But in modern JavaScript, `.toLowerCase()` abstracts away those complexities. Underneath, it uses Unicode mappings to convert characters, so it works with more than just A-Z.

Alternative methods do exist, like:

- `toLocaleLowerCase()`: This respects the user's locale, making it essential for certain languages where the rules of lowercasing are context-specific.

- Regular expressions: Before `toLowerCase()`, developers might have used regex to replace uppercase characters manually.

Details-wise, remember `.toLowerCase()` doesn't change the original string (strings in JavaScript are immutable). You always get a new string. It also handles all characters recognized as uppercase by the Unicode standard, which means you're covered across different languages and scripts.

## See Also
- [MDN web docs on toLowerCase](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase)
- [Unicode standard for casing](https://unicode.org/reports/tr21/tr21-5.html)
- [Upper and lowercase with Locale: toLocaleLowerCase()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLocaleLowerCase)
