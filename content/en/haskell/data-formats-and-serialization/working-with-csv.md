---
aliases:
- /en/haskell/working-with-csv/
date: 2024-02-03 19:03:03.666619-07:00
description: "Working with CSVs (Comma-Separated Values) involves parsing and generating\
  \ files that store tabular data in a simple, text-based format. Programmers\u2026"
lastmod: 2024-02-18 23:09:11.117791
model: gpt-4-0125-preview
summary: "Working with CSVs (Comma-Separated Values) involves parsing and generating\
  \ files that store tabular data in a simple, text-based format. Programmers\u2026"
title: Working with CSV
---

{{< edit_this_page >}}

## What & Why?

Working with CSVs (Comma-Separated Values) involves parsing and generating files that store tabular data in a simple, text-based format. Programmers frequently engage in this task to efficiently import or export data from spreadsheets, databases, or to facilitate data interchange between different programs.

## How to:

In Haskell, handling CSV files can be achieved using the `cassava` library, one of the popular third-party libraries for this purpose. Below are examples showcasing how to read from and write to CSV files using `cassava`.

**1. Reading a CSV file:**

First, ensure you have `cassava` installed by adding it to your project's cabal file or using Stack.

Here's a simple example to read a CSV file and print each record. We assume the CSV file has two columns: name and age.

```haskell
{-# LANGUAGE OverloadedStrings #-}
import Data.Csv
import qualified Data.ByteString.Lazy as BL
import qualified Data.Vector as V

main :: IO ()
main = do
    csvData <- BL.readFile "people.csv"
    case decode NoHeader csvData of
        Left err -> putStrLn err
        Right v -> V.forM_ v $ \(name, age) ->
            putStrLn $ name ++ " is " ++ show (age :: Int) ++ " years old."
```

Assuming `people.csv` contains:
```
John,30
Jane,25
```
The output will be:
```
John is 30 years old.
Jane is 25 years old.
```

**2. Writing a CSV file:**

To create a CSV file, you can use the `encode` function from `cassava`.

Here’s how you could write a list of records to a CSV file:

```haskell
{-# LANGUAGE OverloadedStrings #-}
import Data.Csv
import qualified Data.ByteString.Lazy as BL

main :: IO ()
main = BL.writeFile "output.csv" $ encode [("John", 30), ("Jane", 25)]
```

After running this program, `output.csv` will contain:

```
John,30
Jane,25
```

This concise introduction to working with CSV files in Haskell using the `cassava` library demonstrates how to both read from and write to CSV files, making data manipulation tasks more approachable for those new to the language.
