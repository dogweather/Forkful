---
title:                "Rejestrowanie zdarzeń"
date:                  2024-01-26T01:07:08.374614-07:00
model:                 gpt-4-1106-preview
simple_title:         "Rejestrowanie zdarzeń"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/php/logging.md"
---

{{< edit_this_page >}}

## Co i dlaczego?

Logowanie jest w zasadzie jak prowadzenie dziennika dla twojego kodu; to czynność polegająca na rejestrowaniu zdarzeń, błędów i innych istotnych punktów danych, które pojawiają się, gdy aplikacja jest uruchamiana. Programiści robią to, aby śledzić, co dzieje się w tle, diagnozować problemy oraz utrzymywać ścieżkę audytową do późniejszych analiz lub celów zgodności.

## Jak to zrobić:

PHP posiada wbudowaną funkcję rejestrowania błędów, która jest łatwa w użyciu. Wystarczy umieścić `error_log()` w swoim kodzie, aby wysłać wiadomość do dzienników serwera. Można również dostosować ją do zapisywania w określonym pliku.

```php
<?php
// Logowanie prostej informacji
error_log("To jest wpis loga informacyjnego.");

// Logowanie komunikatu o błędzie
error_log("To jest wpis loga błędu.", 0);

// Logowanie do określonego pliku
file_put_contents('/ścieżka/do/twojego/custom.log', "Wpis własnego loga.\n", FILE_APPEND);

// Użycie Monolog dla strukturyzowanego logowania
require 'vendor/autoload.php';
use Monolog\Logger;
use Monolog\Handler\StreamHandler;

// Stworzenie logera
$logger = new Logger('nazwa');
// Teraz dodajmy kilka handlerów
$logger->pushHandler(new StreamHandler('/ścieżka/do/twojego/monolog.log', Logger::WARNING));

// Teraz możesz użyć swojego logera
$logger->warning('To jest log ostrzeżenia!');
$logger->error('To jest log błędu!');
?>
```

To spowoduje wyjście twoich logów albo do dziennika serwera, albo do określonego pliku w formacie zwykłego tekstu.

## Szczegółowe omówienie:

Historycznie, programiści PHP polegali na funkcji `error_log()` lub logach Apache/Nginx, aby wyłapywać problemy, ale może to być chaotyczne z potrzebą parsowania zwykłych plików tekstowych i brakiem łatwego sposobu na filtrowanie lub sortowanie ich. Tu na scenę wchodzą biblioteki do logowania jak Monolog, które wprowadziły erę strukturyzowanego logowania w PHP. Te rozwiązania dają ci lepszą kontrolę, oferując wiele kanałów logowania, poziomy ważności oraz sformatowane wyjście (takie jak JSON, co jest marzeniem do programistycznego parsowania).

Alternatywy dla Monologa obejmują Log4php, KLogger i Apache's Log4php. Pod względem implementacji, solidne logowanie wymaga nie tylko zrzucania danych gdziekolwiek, ale rozważenia takich rzeczy jak rotacja logów, strategie archiwizacji oraz integracja z narzędziami monitorującymi, aby było naprawdę przydatne.

Powinieneś mieć na uwadze [PSR-3 Logger Interface](https://www.php-fig.org/psr/psr-3/), co określa wspólny interfejs dla bibliotek do logowania, zapewniając interoperacyjność i spójny sposób dostępu do mechanizmów logowania.

## Zobacz również:

- [Repozytorium GitHub Monolog](https://github.com/Seldaek/monolog)
- [Specyfikacja Interfejsu Loggera PSR-3](https://www.php-fig.org/psr/psr-3/)
- [Dokumentacja PHP Error Log](https://www.php.net/manual/en/function.error-log.php)
- [KLogger: Prosta Klasa Logowania Dla PHP](https://github.com/katzgrau/KLogger)
- [Log4php: Wszechstronny framework logowania dla PHP](https://logging.apache.org/log4php/)

Zacznij od wbudowanych funkcji, ale dla bardziej zrównoważonego i skalowalnego podejścia, rozważ zainwestowanie czasu, aby zapoznać się z biblioteką taką jak Monolog. Szczęśliwego logowania!
