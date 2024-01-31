---
title:                "Datum in einen String umwandeln"
date:                  2024-01-20T17:36:02.668344-07:00
model:                 gpt-4-1106-preview
simple_title:         "Datum in einen String umwandeln"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/elixir/converting-a-date-into-a-string.md"
---

{{< edit_this_page >}}

## Was & Warum?
Datum in String umwandeln bedeutet, ein Datum in eine lesbare Zeichenkette zu verwandeln. Das ist praktisch für Ausgaben, Speicherung oder um Datumsinformationen in menschenlesbare Formate zu konvertieren.

## Anleitung:
```elixir
# Ecto für den Umgang mit Datenstrukturen hinzufügen
{:ok, _} = Application.ensure_all_started(:ecto)

# DateTime erstellen
datetime = ~N[2023-03-15 14:30:00]

# DateTime in String konvertieren
string_date = Ecto.DateTime.to_string(datetime)
IO.puts string_date  # Ausgabe: "2023-03-15T14:30:00Z"
```

## Tiefere Einblicke:
Elixir nutzte ursprünglich die `Ecto.DateTime` Bibliothek, übernahm aber später die `DateTime` Struktur direkt ins Kernsystem. Alternativen für die Umwandlung bieten Bibliotheken wie `Timex`. Beim Umwandeln werden häufig ISO 8601-Formate verwendet, welche international standardisierte Beschreibungen für Datum und Zeit bieten.

## Siehe Auch:
- [Elixir's DateTime Dokumentation](https://hexdocs.pm/elixir/DateTime.html)
- [Ecto's Dokumentation](https://hexdocs.pm/ecto/Ecto.html)
- [ISO 8601 Format Erklärung](https://de.wikipedia.org/wiki/ISO_8601)
