---
date: 2024-01-20 17:41:07.135966-07:00
description: "Creare un file temporaneo significa che il tuo programma pu\xF2 tenere\
  \ dei dati temporaneamente durante l'esecuzione. I programmatori fanno questo per\
  \ non\u2026"
lastmod: '2024-03-13T22:44:43.020378-06:00'
model: gpt-4-1106-preview
summary: "Creare un file temporaneo significa che il tuo programma pu\xF2 tenere dei\
  \ dati temporaneamente durante l'esecuzione."
title: Creazione di un file temporaneo
weight: 21
---

## Come si fa:
```Python
import tempfile

# Crea un file temporaneo e scrivici dentro
with tempfile.TemporaryFile(mode='w+t') as tf:
    tf.write('Ciao, mondo!')
    tf.seek(0)  # Torna all'inizio del file
    print(tf.read())  # Leggi il contenuto del file

# Il file temporaneo è stato già eliminato
```
Questo codice stamperà:
```
Ciao, mondo!
```

## Approfondimento
I file temporanei sono usati per molti scopi, dai processi di backup alla manipolazione di dati grossi. Negli anni 80, su sistemi con memorie limitate, era fondamentale ridurre lo spazio su disco usato. Anche oggi, con dischi più grandi, è buona norma per evitare sprechi.

Un'alternativa è usare `tempfile.NamedTemporaryFile()`, che crea un file con un nome visibile nel filesystem, utile se devi passare il file a programmi esterni.

Dettaglio implementativo - in Linux, i file temporanei sono solitamente creati nella directory `/tmp` e possono essere gestiti con ulteriori parametri come `delete=False` se non vuoi che il file venga cancellato quando viene chiuso.

## Vedi anche
- [Python tempfile documentation](https://docs.python.org/3/library/tempfile.html)
- [Understanding Unix/Linux `/tmp` directory](https://www.gnu.org/software/libc/manual/html_node/Temporary-Files.html)
- [Secure coding practices](https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/)
