---
title:                "Refactoring"
aliases:
- en/php/refactoring.md
date:                  2024-01-25T02:12:42.772193-07:00
model:                 gpt-4-1106-preview
simple_title:         "Refactoring"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/php/refactoring.md"
---

{{< edit_this_page >}}

## What & Why?
Refactoring is the process of restructuring existing computer code without changing its external behavior. Programmers refactor to improve nonfunctional attributes of the software, making the code cleaner, more efficient, and easier to maintain.

## How to:
Let's take a classic PHP snippet and apply some refactoring magic to it. 

Before refactoring, our code might look like this:

```php
function printOrderDetails($order) {
    foreach ($order as $item) {
        echo "Item: " . $item['name'];
        echo " - Price: " . $item['price'];
        echo "<br>";
    }
    
    if (!empty($order)) {
        echo "Total: " . array_sum(array_column($order, 'price'));
    }
}
```

But we can refactor this code to improve its clarity and modularity:

```php
function printItem($item) {
    echo "Item: {$item['name']} - Price: {$item['price']}<br>";
}

function calculateTotal($order) {
    return array_sum(array_column($order, 'price'));
}

function printOrderDetails(array $order) {
    array_walk($order, 'printItem');

    if (!empty($order)) {
        echo "Total: " . calculateTotal($order);
    }
}
```
By breaking down the `printOrderDetails` function into smaller functions, our code becomes more readable and easier to debug.

## Deep Dive
Refactoring has its roots in the smalltalk programming community of the early 1990s and was further popularized by Martin Fowler's seminal book "Refactoring: Improving the Design of Existing Code" (1999). While refactoring can be applied to any programming language, PHP's dynamic nature allows for some unique challenges and opportunities.

Alternatives to refactoring might include rewriting code from scratch, which is often riskier and more time-consuming. In the PHP ecosystem, tools like PHPStan and Rector can automatically spot and perform some refactoring operations, respectively. Implementation-wise, keeping refactorings small and testing extensively with unit tests are key practices to ensure successful refactoring without introducing bugs.

## See Also
- Martin Fowler's Refactoring book: https://martinfowler.com/books/refactoring.html
- PHPStan, a PHP static analysis tool: https://phpstan.org/
- Rector, a tool for automatic refactoring of PHP code: https://getrector.org/
- PHP Unit Testing with PHPUnit: https://phpunit.de/
