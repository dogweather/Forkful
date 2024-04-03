---
date: 2024-01-20 17:52:49.178700-07:00
description: "Printing debug output is tossing little bread crumbs of information\
  \ into the console to track down bugs. It's quick, dirty, and effective for\u2026"
lastmod: '2024-03-13T22:44:59.974755-06:00'
model: gpt-4-1106-preview
summary: Printing debug output is tossing little bread crumbs of information into
  the console to track down bugs.
title: Printing debug output
weight: 33
---

## How to:
Let’s get some code on the screen:

```java
public class DebugExample {
    public static void main(String[] args) {
        int sum = 0;
        for (int i = 1; i <= 10; i++) {
            sum += i;
            System.out.println("Added " + i + ", sum now: " + sum);
        }
    }
}
```

This snippet sums numbers from 1 to 10 and prints progress:

```
Added 1, sum now: 1
Added 2, sum now: 3
...
Added 10, sum now: 55
```

## Deep Dive
Back before IDEs got smart, printf-style debugging was the go-to. Even now, amidst fancy breakpoints, sometimes a well-placed `System.out.println()` is all you need to align the planets.

Alternatives? Logging frameworks like Log4J or SLF4J give you control over debug info, separating it from system output and letting you toggle verbosity.

Implementation-wise, remember that `System.out` is a `PrintStream` object, defaulting to stdout. It can be replaced to redirect output, making testing or logging less intrusive.

## See Also
- [Oracle’s Tutorial on I/O Streams](https://docs.oracle.com/javase/tutorial/essential/io/streams.html)
- [Best Practices for Logging in Java](https://www.baeldung.com/java-logging-intro)
- [SLF4J Documentation](http://www.slf4j.org/docs.html)
