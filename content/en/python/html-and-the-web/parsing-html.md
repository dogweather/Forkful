---
title:                "Parsing HTML"
aliases:
- /en/python/parsing-html/
date:                  2024-02-03T19:02:33.698253-07:00
model:                 gpt-4-0125-preview
simple_title:         "Parsing HTML"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/en/python/parsing-html.md"
---

{{< edit_this_page >}}

## What & Why?
Parsing HTML involves analyzing a webpage's HTML code to extract specific information or elements, a common task for web scraping, data mining, or automating interactions with websites. Programmers do it to programmatically interact with or extract data from websites, automate tasks, or test web applications.

## How to:
Python provides powerful libraries like BeautifulSoup and requests for web scraping and HTML parsing. To begin, you need to install these libraries if you haven't already:

```bash
pip install beautifulsoup4 requests
```

Here's a basic example using `requests` to fetch the HTML content of a webpage and `BeautifulSoup` to parse it:

```python
import requests
from bs4 import BeautifulSoup

# Fetch the content of a webpage
URL = 'https://example.com'
page = requests.get(URL)

# Parse the HTML content
soup = BeautifulSoup(page.content, 'html.parser')

# Example of extracting the title of the webpage
title = soup.find('title').text
print(f'Webpage Title: {title}')
```

**Sample output**:
```
Webpage Title: Example Domain
```

For more complex queries, like extracting all links from a webpage, you can use BeautifulSoup's various methods for navigating and searching the parse tree:

```python
# Extract all links within <a> tags
links = soup.find_all('a')

for link in links:
    href = link.get('href')
    print(href)
```

**Sample output**:
```
https://www.iana.org/domains/example
```

BeautifulSoup's flexibility allows you to tailor your search for the exact data needed, making HTML parsing a powerful tool for programmers working with web content.
