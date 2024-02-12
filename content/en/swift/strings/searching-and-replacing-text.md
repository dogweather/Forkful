---
title:                "Searching and replacing text"
aliases:
- /en/swift/searching-and-replacing-text/
date:                  2024-01-20T17:58:44.178581-07:00
model:                 gpt-4-1106-preview
simple_title:         "Searching and replacing text"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/swift/searching-and-replacing-text.md"
---

{{< edit_this_page >}}

## What & Why?

Searching and replacing text in programming is exactly what it sounds like: scanning strings for certain patterns and swapping those out for something else. Programmers do this a lot - for data cleanup, user interface updates, or prepping strings for processing.

## How to:

```Swift
var greetings = "Hello, old friend!"

// Simple replace
greetings = greetings.replacingOccurrences(of: "old", with: "new")
print(greetings) // "Hello, new friend!"

// Using options for case-insensitive replace
let caseInsensitiveResult = greetings.replacingOccurrences(
    of: "hello",
    with: "Hi",
    options: .caseInsensitive
)
print(caseInsensitiveResult) // "Hi, new friend!"

// Replacing with regular expressions
let regexResult = greetings.replacingOccurrences(
    of: "\\bnew\\b",
    with: "best",
    options: .regularExpression
)
print(regexResult) // "Hello, best friend!"
```

## Deep Dive

We've been swapping text in strings since the early days of computing. Initially, it was with simple command-line tools like `sed`. In Swift, `replacingOccurrences(of:with:)` does the heavy lifting, and you get more control with options like `.caseInsensitive` or `.regularExpression`.

Alternatives in Swift include using `NSRegularExpression` for complex patterns and `NSMutableString` for mutable string operations. Under the hood, Swift's string replacement methods bridge to powerful Objective-C counterparts, providing speed and versatility.

## See Also

- [Swift String Documentation](https://developer.apple.com/documentation/swift/string/)
- [Regular Expressions in Swift](https://nshipster.com/swift-regular-expressions/)
- [Swift.org - Working with Strings](https://swift.org/documentation/api-design-guidelines/#strive-for-fluent-usage)
