---
title:                "Generierung von Zufallszahlen"
date:                  2024-01-27T20:34:35.453850-07:00
model:                 gpt-4-0125-preview
simple_title:         "Generierung von Zufallszahlen"
programming_language: "PowerShell"
category:             "PowerShell"
tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/powershell/generating-random-numbers.md"
---

{{< edit_this_page >}}

## Was & Warum?
Die Erzeugung von Zufallszahlen in PowerShell besteht darin, unvorhersehbare numerische Werte innerhalb eines festgelegten Bereichs zu erstellen. Programmierer nutzen diese Fähigkeit aus einer Vielzahl von Gründen, einschließlich Testen, Simulation und Sicherheitszwecken, wo Unvorhersehbarkeit oder das Nachahmen von realer Zufälligkeit entscheidend ist.

## Wie geht das:
PowerShell bietet einen unkomplizierten Ansatz, um Zufallszahlen mit dem Cmdlet `Get-Random` zu generieren. Dieses Cmdlet kann Zufallszahlen in einem Standardbereich oder einem bestimmten Bereich produzieren.

```PowerShell
# Erzeugt eine Zufallszahl zwischen 0 und Int32.MaxValue
$randomNumber = Get-Random
Write-Output $randomNumber
```

Um einen Bereich anzugeben, verwenden Sie die Parameter `-Minimum` und `-Maximum`:

```PowerShell
# Erzeugt eine Zufallszahl zwischen 1 und 100
$randomNumber = Get-Random -Minimum 1 -Maximum 101
Write-Output $randomNumber
```

Für mehr Kontrolle können Sie ein Objekt der `System.Random`-Klasse erstellen:

```PowerShell
# Verwendung von System.Random für eine Reihe von Zahlen
$rand = New-Object System.Random
foreach ($i in 1..5) {
    $randomNumber = $rand.Next(1, 101)
    Write-Output $randomNumber
}
```

Wenn Sie eine zufällige Auswahl aus einem Array oder einer Sammlung benötigen, kann `Get-Random` direkt ein Element auswählen:

```PowerShell
# Zufällige Auswahl aus einem Array
$array = 1..10
$randomItem = Get-Random -InputObject $array
Write-Output $randomItem
```

## Tiefergehende Betrachtung
Das Cmdlet `Get-Random` in PowerShell nutzt unter der Haube die .NET-Klasse `System.Random`, um pseudozufällige Zahlen zu erzeugen. Diese sind "pseudo", weil sie Algorithmen verwenden, um Sequenzen von Zahlen zu produzieren, die nur scheinbar zufällig sind. Für die meisten Anwendungen ist dieses Maß an Zufälligkeit ausreichend. Allerdings ist `System.Random` für Anwendungsfälle, die kryptografische Sicherheit erfordern, aufgrund seiner vorhersehbaren Natur nicht geeignet.

PowerShell und .NET bieten `System.Security.Cryptography.RNGCryptoServiceProvider` für kryptographische Zufälligkeit an, der für die Generierung von Verschlüsselungsschlüsseln oder andere sicherheitskritische Operationen geeigneter ist:

```PowerShell
# Kryptografisch sichere Zufallszahlen
$rng = [System.Security.Cryptography.RNGCryptoServiceProvider]::new()
$bytes = New-Object byte[] 4
$rng.GetBytes($bytes)
$randomNumber = [BitConverter]::ToInt32($bytes, 0)
Write-Output $randomNumber
```

Während `Get-Random` und `System.Random` eine breite Palette von Bedürfnissen nach Zufälligkeit in Skripting und Anwendungslogik erfüllen, ist es wesentlich, das richtige Werkzeug für den Job auszuwählen, insbesondere in sicherheitszentrierten Anwendungen, wo Vorhersehbarkeit eine Schwachstelle darstellen kann.
