---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:56:51.180619-07:00
description: "Wysy\u0142anie \u017C\u0105dania HTTP z podstawow\u0105 autentykacj\u0105\
  \ polega na do\u0142\u0105czeniu nazwy u\u017Cytkownika i has\u0142a do \u017C\u0105\
  dania, w celu weryfikacji to\u017Csamo\u015Bci u\u017Cytkownika.\u2026"
lastmod: '2024-03-13T22:44:35.091121-06:00'
model: gpt-4-0125-preview
summary: "Wysy\u0142anie \u017C\u0105dania HTTP z podstawow\u0105 autentykacj\u0105\
  \ polega na do\u0142\u0105czeniu nazwy u\u017Cytkownika i has\u0142a do \u017C\u0105\
  dania, w celu weryfikacji to\u017Csamo\u015Bci u\u017Cytkownika."
title: "Wysy\u0142anie \u017C\u0105dania HTTP z podstawowym uwierzytelnieniem"
weight: 45
---

## Jak to zrobić:
W Dart można użyć pakietu `http` do wysyłania żądań HTTP z podstawową autentykacją. Najpierw dodaj pakiet `http` do pliku `pubspec.yaml`:

```yaml
dependencies:
  http: ^0.13.4
```

Następnie zaimportuj pakiet w swoim pliku Dart:

```dart
import 'package:http/http.dart' as http;
import 'dart:convert';
```

Aby wysłać żądanie GET z podstawową autentykacją, możesz użyć poniższego kodu:

```dart
Future<void> fetchUserData() async {
  final username = 'twojaNazwaUzytkownika';
  final password = 'twojeHaslo';
  final credentials = base64Encode(utf8.encode('$username:$password'));
  final response = await http.get(
    Uri.parse('https://twojeapi.com/userdata'),
    headers: {
      'Authorization': 'Basic $credentials',
    },
  );

  if (response.statusCode == 200) {
    print('Pobrano dane użytkownika pomyślnie!');
    print('Odpowiedź serwera: ${response.body}');
  } else {
    print('Nie udało się pobrać danych użytkownika, kod błędu: ${response.statusCode}');
  }
}
```

Ten kod wysyła żądanie GET na adres 'https://twojeapi.com/userdata' z nagłówkiem autentykacji podstawowej. Nazwa użytkownika i hasło są kodowane w base64 i przekazywane w nagłówku 'Authorization' zgodnie ze standardami podstawowego dostępu autentykacyjnego.

**Przykładowe wyjście:**

Po pomyślnym zapytaniu i jeśli serwer zwróci kod stanu 200, możesz zobaczyć:

```plaintext
Pobrano dane użytkownika pomyślnie!
Odpowiedź serwera: {"id":1, "name":"John Doe", "email":"john@example.com"}
```

Jeśli autentykacja się nie powiedzie lub wystąpi jakiś inny błąd, kod stanu odpowiedzi pomoże zidentyfikować problem.
