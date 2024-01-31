---
title:                "Lancement d'un nouveau projet"
date:                  2024-01-20T18:04:00.011521-07:00
model:                 gpt-4-1106-preview
simple_title:         "Lancement d'un nouveau projet"

tag:                  "Getting Started"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/powershell/starting-a-new-project.md"
---

{{< edit_this_page >}}

## What & Why? (Quoi et Pourquoi ?)
Démarrer un nouveau projet, c'est créer un espace de travail vide pour vos idées de code. Les programmeurs font ça pour organiser et isoler le boulot sur une feature ou une app spécifique.

## How to: (Comment faire :)
```PowerShell
# Création d'un nouveau dossier pour le projet
New-Item -Path 'C:\mes_projets\MonNouveauProjet' -ItemType Directory

# Déplacement dans le dossier du projet
Set-Location -Path 'C:\mes_projets\MonNouveauProjet'

# Initialisation d'un dépôt Git (si vous utilisez Git)
git init

# Output attendu pour git init :
# Initialized empty Git repository in C:/mes_projets/MonNouveauProjet/.git/
```

## Deep Dive (Plongée Profonde)
Historiquement, les projets étaient moins isolés, causant des conflits entre différentes applications. PowerShell, en tant que framework de gestion de tâches et de configuration, facilite la création d'environnements isolés. Des alternatives incluent des outils comme Yeoman pour des projets spécifiques ou même `dotnet new` pour des projets .NET. L'implémentation varie selon les besoins : un scripteur peut simplement créer un dossier, tandis qu'un développeur .NET pourrait configurer toute une solution avec des projets liés.

## See Also (Voir Aussi)
- [Document officiel PowerShell New-Item](https://docs.microsoft.com/fr-fr/powershell/module/microsoft.powershell.management/new-item)
- [Guide pratique Git – Commencer un nouveau dépôt](https://git-scm.com/book/fr/v2/D%C3%A9marrage-rapide-Enregistrement-des-modifications-dans-le-d%C3%A9p%C3%B4t)
- [Page de Yeoman](http://yeoman.io/)
- [Commencer avec .NET CLI](https://docs.microsoft.com/fr-fr/dotnet/core/tools/dotnet-new)
