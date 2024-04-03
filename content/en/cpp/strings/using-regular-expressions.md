---
date: 2024-02-03 19:02:48.448800-07:00
description: "Regular expressions in C++ are sequences of characters that define a\
  \ search pattern, used for string matching or manipulation. Programmers use them\
  \ for\u2026"
lastmod: '2024-03-13T22:45:00.348846-06:00'
model: gpt-4-0125-preview
summary: Regular expressions in C++ are sequences of characters that define a search
  pattern, used for string matching or manipulation.
title: Using regular expressions
weight: 11
---

## How to:
C++11 introduced support for regular expressions in the standard library, `<regex>`, offering a robust framework for string searching and manipulation. Here's a basic example of using regular expressions to search for a pattern within a string:

```cpp
#include <iostream>
#include <regex>

int main() {
    std::string target = "Hello, my email is example@example.com";
    std::regex email_pattern(R"(\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}\b)");

    if (std::regex_search(target, email_pattern)) {
        std::cout << "Email found!" << std::endl;
    } else {
        std::cout << "No email found." << std::endl;
    }

    return 0;
}
```
**Sample Output**
```
Email found!
```

For more complex manipulations, such as replacing patterns within strings, C++’s regular expressions can be very handy:

```cpp
#include <iostream>
#include <regex>

int main() {
    std::string text = "The rain in Spain falls mainly in the plain.";
    std::regex vowel_regex("([aeiou])");

    std::string replaced_text = std::regex_replace(text, vowel_regex, "*");
    std::cout << replaced_text << std::endl;

    return 0;
}
```
**Sample Output**
```
Th* r**n *n Sp**n f*lls m**nly *n th* pl**n.
```

For programmers exploring beyond the standard library, the Boost Regex library (`boost/regex.hpp`) is a popular third-party option offering enhanced regex capabilities and performance optimizations, particularly for complex patterns or extensive data processing:

```cpp
#include <iostream>
#include <boost/regex.hpp>

int main() {
    std::string s = "Boost libraries are fun!";
    boost::regex expr("(\\w+)\\s(libraries)"); // Match "Boost libraries"
    std::string fmt("GNU \\1"); // Replace with "GNU Boost"

    std::string result = boost::regex_replace(s, expr, fmt);
    std::cout << result << std::endl;

    return 0;
}
```
**Sample Output**
```
GNU Boost are fun!
```

These examples scratch the surface of C++'s capabilities with regular expressions, illustrating basic searches, pattern matching, and replacements, either using the standard library or enhanced by Boost's powerful regex implementation.
