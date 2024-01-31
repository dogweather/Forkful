---
title:                "Generating random numbers"
date:                  2024-01-27T20:26:17.584635-07:00
model:                 gpt-4-0125-preview
simple_title:         "Generating random numbers"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/clojure/generating-random-numbers.md"
---

{{< edit_this_page >}}

## What & Why?

Generating random numbers in programming is about creating values that cannot be predicted logically ahead of time. Programmers do this for a variety of reasons, including generating unique identifiers, simulating scenarios in game development, or selecting random samples from data for analysis.

## How to:

In Clojure, random number generation is straightforward, and there are a couple of built-in functions that can be used right away.

To generate a random floating-point number between 0 (inclusive) and 1 (exclusive), you can use the `rand` function:

```Clojure
(rand)
;; Example output: 0.7094245047062917
```

If you need an integer within a specific range, use `rand-int`:

```Clojure
(rand-int 10)
;; Example output: 7
```

This gives you a random integer between 0 (inclusive) and the number you pass as an argument (exclusive).

For generating a random number within a specific range (not limited to integers), you can combine `rand` with arithmetic:

```Clojure
(defn rand-range [min max]
  (+ min (* (rand) (- max min))))
;; Usage
(rand-range 10 20)
;; Example output: 14.857457734992847
```

This function `rand-range` will return a random floating-point number between the `min` and `max` values you specify.

For scenarios requiring more complex distributions or sequences of random numbers where repeatability is necessary (using seeds), you might need to look into additional libraries that extend beyond what's built-in.

## Deep Dive

The underlying mechanism for generating random numbers in most programming languages, including Clojure, typically relies on a pseudo-random number generator (PRNG). A PRNG uses an algorithm to produce a sequence of numbers that approximates the properties of random numbers. It's worth noting that because these are algorithmically generated, they are not truly random but can be sufficient for most practical purposes.

In the early days of computing, generating high-quality random numbers was a significant challenge, leading to the development of various algorithms to improve randomness and distribution. For Clojure, the built-in functions, such as `rand` and `rand-int`, are convenient for everyday use and cover a broad spectrum of common use cases.

However, for applications requiring cryptographic security or more complex statistical sampling methods, Clojure developers often turn to external libraries that offer more robust and specialized PRNGs. Libraries such as `clj-random` provide access to a wider variety of algorithms and greater control over seeding, which can be crucial for simulations, cryptographic applications, or any domain where the quality and predictability of the random number sequence could have significant implications.

While Clojure's built-in capabilities for generating random numbers are adequate for many tasks, exploring external libraries can offer deeper insights and options for tailored or more critical applications.
