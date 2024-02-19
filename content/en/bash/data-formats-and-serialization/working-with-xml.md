---
aliases:
- /en/bash/working-with-xml/
date: 2024-01-25 03:39:52.357960-07:00
description: "Working with XML involves parsing, extracting, and manipulating data\
  \ in the Extensible Markup Language format. Programmers wrestle with XML since it's\
  \ a\u2026"
lastmod: 2024-02-18 23:09:11.254103
model: gpt-4-1106-preview
summary: "Working with XML involves parsing, extracting, and manipulating data in\
  \ the Extensible Markup Language format. Programmers wrestle with XML since it's\
  \ a\u2026"
title: Working with XML
---

{{< edit_this_page >}}

## What & Why?
Working with XML involves parsing, extracting, and manipulating data in the Extensible Markup Language format. Programmers wrestle with XML since it's a widespread data interchange format for configs, APIs, and more.

## How to:
Here's how to parse XML in Bash. Tools? xmllint and xmlstarlet. Looping through XML elements? Definitely. Example with sample output:

```bash
# Assuming xmlstarlet is installed
# Install with: apt-get install xmlstarlet

# Parsing XML content
cat <<EOF > sample.xml
<fruits>
  <fruit name="Apple"/>
  <fruit name="Banana"/>
</fruits>
EOF

# Extract names with xmlstarlet
xmlstarlet sel -t -m "//fruit" -v "@name" -n sample.xml

# Output should be:
# Apple
# Banana
```

## Deep Dive
Back in the '90s, XML popped up as a simpler alternative to SGML, but more structured than HTML. Now, it's got company – JSON, YAML, for instance. But XML's still kicking, especially in configs and SOAP-based web services. 

Tool-wise, xmllint is comfy for XML validation, xpath queries. xmlstarlet is the swiss-army knife for XML shenanigans – query, edit, validate, transform. In bash scripts, they're superheroes for XML tasks.

Under the hood, xmllint uses libxml2 – the XML C parser. It's fast, but the error messages? Cryptic. And xmlstarlet? Recursive templates and the EXSLT support. Mind bender, but powerful.

## See Also
- [xmlsoft.org](http://xmlsoft.org/): Libxml2 and xmllint stuff.
- [Stack Overflow](https://stackoverflow.com/questions/tagged/xml+bash): Real-world problems and solutions.
- [W3Schools XML Tutorial](https://www.w3schools.com/xml/): Basics of XML.
