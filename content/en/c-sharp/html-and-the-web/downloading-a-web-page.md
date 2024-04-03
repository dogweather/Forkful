---
date: 2024-01-20 17:43:35.028671-07:00
description: "Downloading a web page means grabbing the raw HTML content from the\
  \ internet using code. Programmers do this to process data, interact with web services,\u2026"
lastmod: '2024-03-13T22:45:00.087516-06:00'
model: gpt-4-1106-preview
summary: Downloading a web page means grabbing the raw HTML content from the internet
  using code.
title: Downloading a web page
weight: 42
---

## How to:
C# makes it simple to download a web page with the `HttpClient` class. Here's a quick example:

```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (HttpClient client = new HttpClient())
        {
            try
            {
                string url = "http://example.com"; // Replace with the desired URL
                HttpResponseMessage response = await client.GetAsync(url);
                response.EnsureSuccessStatusCode();
                string responseBody = await response.Content.ReadAsStringAsync();
                
                Console.WriteLine(responseBody); // Outputs the raw HTML content
            }
            catch (HttpRequestException e)
            {
                Console.WriteLine("\nException Caught!");
                Console.WriteLine("Message :{0} ", e.Message);
            }
        }
    }
}
```

This will output HTML content of the specified web page into the console.

## Deep Dive
Before `HttpClient`, C# used classes like `WebClient` and `HttpWebRequest` to download web content. `HttpClient` is the latest and is designed to be reusable, efficient, and support asynchronous operations making it the preferred choice for new applications.

Alternatives exist. For instance, third-party libraries such as `HtmlAgilityPack` can parse HTML, making it easier to navigate the DOM or extract specific pieces of info without dealing with raw HTML strings.

When downloading web pages, remember: respect robots.txt files, handle exceptions, and be mindful of the terms of use for websites.

## See Also
- [HttpClient Class Documentation](https://docs.microsoft.com/en-us/dotnet/api/system.net.http.httpclient)
- [Async and Await](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/async/)
- [HTML Agility Pack on GitHub](https://github.com/zzzprojects/html-agility-pack)
- [Respecting robots.txt](https://developers.google.com/search/docs/advanced/robots/intro)
