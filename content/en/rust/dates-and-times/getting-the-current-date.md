---
title:                "Getting the current date"
aliases:
- /en/rust/getting-the-current-date/
date:                  2024-02-03T19:02:38.356621-07:00
model:                 gpt-4-0125-preview
simple_title:         "Getting the current date"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/rust/getting-the-current-date.md"
---

{{< edit_this_page >}}

## What & Why?

Retrieving the current date in Rust is a common task for tasks such as logging, time-based operations, or simply displaying the date. Unlike some languages that include date and time functionality in their standard library, Rust encourages the use of a robust third-party library, chrono, for comprehensive date and time manipulation due to its superior functionality and ease of use.

## How to:

### Using Rust's Standard Library
Rust's standard library provides a limited but quick way to get the current time, though not directly the current date in a calendar format. Here's how you do it:

```rust
use std::time::{SystemTime, UNIX_EPOCH};

fn main() {
    match SystemTime::now().duration_since(UNIX_EPOCH) {
        Ok(n) => println!("Current time: {} seconds since the Unix Epoch.", n.as_secs()),
        Err(_) => panic!("SystemTime before Unix Epoch!"),
    }
}
```

Output:
```
Current time: 1615390665 seconds since the Unix Epoch.
```

### Using the Chrono Library
For more comprehensive date and time functionality, including getting the current date, you should use the `chrono` library. First, add `chrono` to your `Cargo.toml`:

```toml
[dependencies]
chrono = "0.4"
```

Then, you can use `chrono` to get the current date:

```rust
extern crate chrono;
use chrono::{Local, Datelike};

fn main() {
    let now = Local::now();
    println!("Current date: {}-{}-{}", now.year(), now.month(), now.day());
}
```

Output:
```
Current date: 2023-4-20
```

The `chrono` library makes it straightforward to work with dates and times, offering a wide range of functionalities beyond just retrieving the current date, including parsing, formatting, and arithmetic operations on dates and times.
