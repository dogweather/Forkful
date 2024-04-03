---
date: 2024-02-03 19:02:35.355748-07:00
description: "Checking if a directory exists is about determining the presence of\
  \ a directory at a specified path before performing operations like reading from\
  \ or\u2026"
lastmod: '2024-03-13T22:45:00.370486-06:00'
model: gpt-4-0125-preview
summary: Checking if a directory exists is about determining the presence of a directory
  at a specified path before performing operations like reading from or writing to
  files within it.
title: Checking if a directory exists
weight: 20
---

## How to:
In modern C++ (C++17 and beyond), you can use the filesystem library to check if a directory exists. It provides a straightforward and standardized way to perform filesystem operations, including checking for the existence of a directory.

```cpp
#include <iostream>
#include <filesystem>

namespace fs = std::filesystem;

int main() {
    const fs::path dirPath = "/path/to/directory";

    if (fs::exists(dirPath) && fs::is_directory(dirPath)) {
        std::cout << "The directory exists." << std::endl;
    } else {
        std::cout << "The directory does not exist." << std::endl;
    }

    return 0;
}
```
Sample output if the directory exists:
```
The directory exists.
```

Sample output if the directory does not exist:
```
The directory does not exist.
```

For projects that are not yet using C++17 or for additional features, the Boost Filesystem library is a popular third-party choice that offers similar functionality. 

```cpp
#include <iostream>
#include <boost/filesystem.hpp>

namespace fs = boost::filesystem;

int main() {
    const fs::path dirPath = "/path/to/directory";

    if (fs::exists(dirPath) && fs::is_directory(dirPath)) {
        std::cout << "The directory exists." << std::endl;
    } else {
        std::cout << "The directory does not exist." << std::endl;
    }

    return 0;
}
```
Using Boost Filesystem, the output would be identical to the C++17 filesystem example, depending on the existence of the directory at the specified path.
