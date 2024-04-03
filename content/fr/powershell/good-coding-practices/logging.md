---
date: 2024-01-26 01:07:40.281848-07:00
description: "Le logging, c'est fondamentalement laisser une tra\xEEn\xE9e de miettes\
  \ \xE0 travers votre code - c'est la mani\xE8re de garder un \u0153il sur ce qui\
  \ se passe lorsque\u2026"
lastmod: '2024-03-13T22:44:58.056835-06:00'
model: gpt-4-1106-preview
summary: "Le logging, c'est fondamentalement laisser une tra\xEEn\xE9e de miettes\
  \ \xE0 travers votre code - c'est la mani\xE8re de garder un \u0153il sur ce qui\
  \ se passe lorsque votre script est ex\xE9cut\xE9 en production."
title: Journalisation
weight: 17
---

## Comment faire :
Voici le b.a.-ba pour intégrer du logging basique dans vos scripts :

```PowerShell
# Créer un message de log simple
Write-Host "Info: Démarrage du processus du script."

# Écrire dans un fichier
"Info: Ceci est un message logué." | Out-File -Append myLog.log

# Utiliser le cmdlet intégré pour un logging plus détaillé
Start-Transcript -Path "./detailedLog.log"
Write-Output "Attention: Quelque chose ne va pas tout à fait bien."
# ... votre script fait des choses
Stop-Transcript

# Sortie de detailedLog.log
******************************
Transcription de PowerShell Windows commence
Heure de début : 20230324112347
Nom d'utilisateur : PShellGuru@example.com
Utilisateur exécuté comme : PShellGuru@example.com
Nom de la configuration : 
Machine : PS-DEVBOX (Microsoft Windows NT 10.0.17763.0)
Application hôte : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
ID du processus : 2024
Version de PS : 7.1.2
```

Maintenant, dans vos logs, il y a un compte-rendu détaillé de ce que votre code a réalisé.

## Plongée en profondeur :
Historiquement, le logging est presque aussi vieux que la programmation elle-même. C'est comme le journal de bord d'un capitaine, mais pour les logiciels. Auparavant, cela aurait pu être des impressions ou des machines de télétypage ; maintenant, c'est tout sur les fichiers et des systèmes de gestion de logs sophistiqués.

Quand vous êtes dans les tranchées de PowerShell, `Write-Host` est rapide et sale, mais il se contente d'afficher du texte dans la console, ce qui n'est pas idéal pour conserver des enregistrements. `Out-File` vous offre un moyen simple d'envoyer du texte dans un fichier, mais pour le vrai nectar, vous voudrez utiliser `Start-Transcript` et `Stop-Transcript` qui loguent tout – entrées, sorties, le tout.

Des alternatives ? Bien sûr. Si vous travaillez dans une grande entreprise, vous pourriez envisager Windows Event Log ou utiliser des logiciels comme Logstash, mais pour vos scripts de tous les jours, tenez-vous-en aux outils de PowerShell. Concernant la mise en œuvre, souvenez-vous de loguer intelligemment – trop peu et c'est inutile, trop et c'est un bruit de fond.

## Voir aussi :
Consultez ces ressources pour maîtriser tout ce qui concerne les logs dans PowerShell :
