---
aliases:
- /en/powershell/working-with-xml/
date: 2024-01-25 03:39:46.745957-07:00
description: "Working with XML involves manipulating and accessing data structured\
  \ in the eXtensible Markup Language. Programmers work with XML to enable\u2026"
lastmod: 2024-02-18 23:09:11.298142
model: gpt-4-1106-preview
summary: "Working with XML involves manipulating and accessing data structured in\
  \ the eXtensible Markup Language. Programmers work with XML to enable\u2026"
title: Working with XML
---

{{< edit_this_page >}}

## What & Why?
Working with XML involves manipulating and accessing data structured in the eXtensible Markup Language. Programmers work with XML to enable interoperability with other systems or to read and write configuration files, data feeds, and other structured documents common in web services.

## How to:
```PowerShell
# Loading an XML file into a variable
[xml]$xmlContent = Get-Content 'path\to\your\file.xml'

# Accessing XML nodes
$books = $xmlContent.catalog.book
foreach ($book in $books) {
  Write-Output "Title: $($book.title)"
}

# Creating a new XML element
$newBook = $xmlContent.CreateElement("book")
$newBook.SetAttribute("id", "bk999")
$xmlContent.DocumentElement.AppendChild($newBook)

# Saving the XML back to file
$xmlContent.Save('path\to\your\updated\file.xml')
```
Sample Output:
```
Title: Programming PowerShell
Title: XML Essentials
```

## Deep Dive
XML, or eXtensible Markup Language, has been around since the late '90s and remains a widely-used format for structured data. PowerShell simplifies working with XML compared to traditional parsing methods; it casts XML to objects directly, letting you interact with elements through familiar dot notation.

Alternatives to XML include JSON, YAML, or custom data formats. JSON, for instance, has gained popularity for its lightweight nature and ease of use with web technologies. However, XML's extended features like namespaces, schemas, and XSLT processing often make it a better fit for complex documents or industry standards.

PowerShell uses the .NET Framework's XML capabilities for its XML handling. This means it's not just about simple read-write operations; you can also work with XML schemas for validation, use XPath for queries, and employ XSLT transformations, all through PowerShell.

## See Also
- [W3Schools XML tutorial](https://www.w3schools.com/xml/)
- [XML vs. JSON](https://www.json.org/json-en.html)
