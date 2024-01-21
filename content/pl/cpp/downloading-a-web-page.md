---
title:                "Pobieranie strony internetowej"
date:                  2024-01-20T17:43:42.854802-07:00
model:                 gpt-4-1106-preview
simple_title:         "Pobieranie strony internetowej"
programming_language: "C++"
category:             "C++"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/cpp/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## What & Why? (Co i Dlaczego?)
Pobieranie strony internetowej to proces ściągania danych z sieci - jakbyś kopiował tekst ze stronki internetowej prosto do swojego programu. Programiści robią to, aby przetwarzać informacje online, aktualizować dane lub po prostu zgrać zawartość.

## How to: (Jak to zrobić:)
```C++
#include <iostream>
#include <curl/curl.h>

static size_t WriteCallback(void *contents, size_t size, size_t nmemb, void *userp) {
    ((std::string*)userp)->append((char*)contents, size * nmemb);
    return size * nmemb;
}

int main() {
    CURL *curl;
    CURLcode res;
    std::string readBuffer;

    curl = curl_easy_init();
    if(curl) {
        curl_easy_setopt(curl, CURLOPT_URL, "http://example.com");
        curl_easy_setopt(curl, CURLOPT_WRITEFUNCTION, WriteCallback);
        curl_easy_setopt(curl, CURLOPT_WRITEDATA, &readBuffer);
        res = curl_easy_perform(curl);
        curl_easy_cleanup(curl);

        std::cout << readBuffer << std::endl;
    }
    return 0;
}
```
Sample output:
```
<!doctype html>
<html>
<head>
    <title>Example Domain</title>
...
</html>
```

## Deep Dive (Głębsze spojrzenie)
W latach 90. pobieranie stron internetowych było znacznie prostsze ze względu na mniej dynamiczne treści. Dziś, z AJAX i dynamicznym ładowaniem treści, często po prostu ściągnięcie HTML nie wystarcza. Alternatywy jak Selenium czy PhantomJS pozwalają na interakcję ze stroną i jej JavaScriptem. Podczas korzystania z biblioteki cURL w C++, musimy zadbać o zarządzanie pamięcią i bezpieczeństwo - ważna jest odpowiednia konfiguracja i obsługa błędów.

## See Also (Zobacz także)
- Official cURL website: [https://curl.haxx.se](https://curl.haxx.se)
- cURL for C++ tutorial: [http://docs.libcurl.org](http://docs.libcurl.org)
- Web scraping with C++: [https://en.cppreference.com/w/](https://en.cppreference.com/w/cpp)
- Handling JSON in C++: [https://github.com/nlohmann/json](https://github.com/nlohmann/json)
- Selenium WebDriver with C++: [https://www.selenium.dev/](https://www.selenium.dev/)