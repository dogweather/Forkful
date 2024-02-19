---
aliases:
- /fr/powershell/using-regular-expressions/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:17:36.979692-07:00
description: "Les expressions r\xE9guli\xE8res (regex) sont des s\xE9quences de caract\xE8\
  res qui forment un motif de recherche, principalement utilis\xE9es pour la recherche\
  \ et la\u2026"
lastmod: 2024-02-18 23:09:09.054697
model: gpt-4-0125-preview
summary: "Les expressions r\xE9guli\xE8res (regex) sont des s\xE9quences de caract\xE8\
  res qui forment un motif de recherche, principalement utilis\xE9es pour la recherche\
  \ et la\u2026"
title: "Utilisation des expressions r\xE9guli\xE8res"
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?

Les expressions régulières (regex) sont des séquences de caractères qui forment un motif de recherche, principalement utilisées pour la recherche et la manipulation de chaînes de caractères. Les programmeurs utilisent les regex dans PowerShell pour des tâches comme la validation de données, l'analyse et la transformation, en raison de leur efficacité et leur flexibilité dans la gestion des motifs complexes.

## Comment :

Dans PowerShell, vous pouvez utiliser les opérateurs `-match`, `-replace` et `-split`, entre autres, pour effectuer des actions avec des expressions régulières. Explorons quelques exemples :

### Utilisation de `-match` pour vérifier si une chaîne correspond à un motif
Cet opérateur retourne `$true` si le motif est trouvé dans la chaîne, et `$false` autrement.

```powershell
"hello world" -match "\w+orld"
# Sortie : True
```

### Extraction des correspondances
Vous pouvez extraire la valeur correspondante en accédant à la variable automatique `$matches`.

```powershell
if ("J'ai 100 pommes" -match "\d+") {
    "Nombre trouvé : " + $matches[0]
}
# Sortie : Nombre trouvé : 100
```

### Utilisation de `-replace` pour des substitutions
L'opérateur `-replace` remplace toutes les occurrences d'un motif par une chaîne de remplacement spécifiée.

```powershell
"foo bar baz" -replace "ba[rz]", "qux"
# Sortie : foo qux qux
```

### Scinder des chaînes avec `-split`
Scinde une chaîne en un tableau de sous-chaînes basé sur un motif regex.

```powershell
"The quick-brown_fox jumps" -split "[-_ ]"
# Sortie : The quick brown fox jumps
```

### Correspondance de motifs avancée
PowerShell prend également en charge des opérations regex plus complexes via la classe `[regex]`, vous donnant accès à des méthodes telles que `Matches()`, `Replace()`, et `Split()`.

```powershell
[regex]::Matches("Juin 24, Août 9, Déc 12", "\b[A-Za-z]+\b").Value
# Sortie : Juin Août Déc

[regex]::Replace("100,000", "\B(?=(?:\d{3})+(?!\d))", ",")
# Sortie : 100,000

[regex]::Split("un,deux;trois quatre", ",|;| ")
# Sortie : un deux trois quatre
```

Ces exemples montrent la puissance et la polyvalence des expressions régulières dans PowerShell pour la manipulation de données et la correspondance de motifs. En exploitant les regex, les programmeurs peuvent effectuer un traitement de texte complexe de manière efficace.
