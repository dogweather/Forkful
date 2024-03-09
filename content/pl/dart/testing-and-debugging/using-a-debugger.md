---
title:                "Korzystanie z debugera"
date:                  2024-03-08T21:57:06.532837-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?

Użycie debugera w Darcie pozwala programistom metodycznie zbadać swój kod poprzez ustawianie punktów przerwania, krokowe przechodzenie przez wykonanie i inspekcję zmiennych. Proces ten jest niezbędny do identyfikowania i naprawiania błędów w sposób efektywny, czyniąc go niezastąpionym narzędziem w cyklu życia rozwoju.

## Jak to zrobić:

### Podstawowe debugowanie:

**1. Ustawianie punktów przerwania:**

Aby ustawić punkt przerwania, wystarczy kliknąć na lewym marginesie linii kodu w swoim IDE (np. Visual Studio Code lub Android Studio), gdzie chcesz, aby wykonanie zostało wstrzymane.

```dart
void main() {
  var message = 'Hello, Debugging';
  print(message); // Ustaw tutaj punkt przerwania
}
```

**2. Rozpoczynanie debugowania:**

W swoim IDE zainicjuj sesję debugowania, klikając na ikonę debugowania lub naciskając przycisk debugowania. Wykonanie zostanie wstrzymane w punktach przerwania.

**3. Inspekcja zmiennych:**

Gdy wykonanie jest wstrzymane, najedź kursorem na zmienne, aby zobaczyć ich aktualne wartości.

**4. Krokowe przechodzenie przez kod:**

Użyj poleceń krok dalej, krok do środka i krok na zewnątrz w swoim IDE, aby nawigować przez swój kod linia po linii lub funkcja po funkcji.

### Zaawansowane debugowanie z użyciem Observatory:

Dart zawiera narzędzie o nazwie Observatory do debugowania i profilowania aplikacji Dart. Jest szczególnie przydatne dla aplikacji działających na Dart VM.

**Dostęp do Observatory:**

Uruchom swoją aplikację Dart z flagą `--observe`.

```bash
dart --observe your_program.dart
```

To polecenie wyświetla URL w konsoli, który możesz otworzyć w przeglądarce internetowej, aby uzyskać dostęp do debugera Observatory.

### Używanie popularnych bibliotek stron trzecich:

Do debugowania aplikacji Flutter pakiet `flutter_devtools` oferuje zestaw narzędzi do analizy wydajności i debugowania, które integrują się zarówno z Dart VM, jak i Flutter.

**Instalacja:**

Najpierw dodaj `devtools` do pliku `pubspec.yaml` w sekcji `dev_dependencies`:

```yaml
dev_dependencies:
  devtools: any
```

**Uruchamianie DevTools:**

Uruchom to polecenie w terminalu:

```bash
flutter pub global run devtools
```

Następnie uruchom swoją aplikację Flutter w trybie debugowania. DevTools oferuje funkcje takie jak inspektor Fluttera do analizy drzewa widgetów i profilera sieci do monitorowania aktywności sieciowej.

### Przykładowe wyjście:

Po trafieniu na punkt przerwania, twoje IDE może wyświetlić wartości zmiennych i ślady stosu w ten sposób:

```
message: 'Hello, Debugging'
```

Efektywne wykorzystanie narzędzi i technik debugowania w Darcie pozwala programistom szybciej identyfikować i rozwiązywać problemy, prowadząc do płynniejszego procesu rozwoju i tworzenia bardziej solidnych aplikacji.
