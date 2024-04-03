---
date: 2024-01-20 17:54:59.824232-07:00
description: "Reading a text file in PHP means pulling content from a file into your\
  \ script. Programmers do this to handle data storage, configuration, or to process\u2026"
lastmod: '2024-03-13T22:45:00.182832-06:00'
model: gpt-4-1106-preview
summary: Reading a text file in PHP means pulling content from a file into your script.
title: Reading a text file
weight: 22
---

## How to:


### Using `file_get_contents`:
```PHP
$content = file_get_contents("example.txt");
echo $content;
```
Sample Output:
```
Hello, World!
This is content from the text file.
```

### Using `fopen` and `fgets`:
```PHP
$handle = fopen("example.txt", "r");
if ($handle) {
    while (($line = fgets($handle)) !== false) {
        echo $line;
    }
    fclose($handle);
}
```
Sample Output:
```
Hello, World!
This is content from the text file.
```

### Writing to a file with `file_put_contents`:
```PHP
$newContent = "Adding new text.";
file_put_contents("example.txt", $newContent);
```

## Deep Dive
Reading text files is as old as programming itself. Before databases, config files, and user data often lived in simple text files. Alternatives like XML and JSON files are structured, easier to parse, and well-suited for complex data.

In PHP, `file_get_contents` and `file()` are quick for reading; the former gets everything in one string, and the latter in an array. `fopen` coupled with `fgets` or `fread` gives you more control, particularly for large files, as you read it line-by-line or in chunks.

Some nuances: `fopen` requires appropriate permissions, or it'll fail; handling its errors is a best practice. When using `file_put_contents`, be aware it overwrites the file by default; use the `FILE_APPEND` flag to add content instead.

## See Also
- PHP Manual on `file_get_contents`: https://www.php.net/manual/en/function.file-get-contents.php
- PHP Manual on `fopen`: https://www.php.net/manual/en/function.fopen.php
- PHP Manual on `fgets`: https://www.php.net/manual/en/function.fgets.php
- PHP Manual on `file_put_contents`: https://www.php.net/manual/en/function.file-put-contents.php
- Tutorial on PHP file handling: https://www.w3schools.com/php/php_file.asp
