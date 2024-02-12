---
title:                "Searching and replacing text"
date:                  2024-01-20T17:57:56.838430-07:00
model:                 gpt-4-1106-preview
simple_title:         "Searching and replacing text"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/javascript/searching-and-replacing-text.md"
---

{{< edit_this_page >}}

## What & Why?
Searching and replacing text means finding specific substrings and swapping them out for something new. Why bother? It's everywhere: fixing typos in a document, refining code, or batch editing data.

## How to:
In JavaScript, `String.prototype.replace()` is the go-to. Pass a string or regex and the replacement. Here's the quick and dirty:

```javascript
let str = "I love to code in JavaScript!";
let newStr = str.replace("JavaScript", "TypeScript");
console.log(newStr); // Outputs: I love to code in TypeScript!
```

Now, with regex for global replaces:

```javascript
let story = "The quick brown fox jumps over the lazy dog. The fox is clever.";
let newStory = story.replace(/fox/g, "cat");
console.log(newStory); // Outputs: The quick brown cat jumps over the lazy dog. The cat is clever.
```

## Deep Dive
Looking back, `String.prototype.replace()` has been in JS since the early days—Netscape 2 early. Now, ES6 brought us template literals and arrow functions, which spiced things up with more concise and readable code using regex.

Alternatives? Sure. If you're working with large-scale text processing, you might sidestep into Node.js streams or leverage external libraries to handle complex patterns, efficiency, and performance.

As for implementation, `replace()` alone is simple. But regex patterns can get wild. Start easy, learn the special characters (`.` matches any char, `*` for repeating patterns), and test with tools like regex101.

## See Also
- MDN replace documentation: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace
- Regex101 for testing expressions: https://regex101.com/
- JavaScript info on regex: https://javascript.info/regexp-introduction
