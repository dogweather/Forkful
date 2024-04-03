---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:06:52.263272-07:00
description: "Verificare l'esistenza di una directory significa determinare la presenza\
  \ di una directory in un percorso specificato prima di eseguire operazioni come\u2026"
lastmod: '2024-03-13T22:44:43.742110-06:00'
model: gpt-4-0125-preview
summary: Verificare l'esistenza di una directory significa determinare la presenza
  di una directory in un percorso specificato prima di eseguire operazioni come leggere
  o scrivere file al suo interno.
title: Verifica se una directory esiste
weight: 20
---

## Come fare:
Nel C++ moderno (C++17 e versioni successive), puoi utilizzare la libreria filesystem per verificare se una directory esiste. Fornisce un modo diretto e standardizzato per eseguire operazioni sul filesystem, inclusa la verifica dell'esistenza di una directory.

```cpp
#include <iostream>
#include <filesystem>

namespace fs = std::filesystem;

int main() {
    const fs::path dirPath = "/path/to/directory";

    if (fs::exists(dirPath) && fs::is_directory(dirPath)) {
        std::cout << "La directory esiste." << std::endl;
    } else {
        std::cout << "La directory non esiste." << std::endl;
    }

    return 0;
}
```
Output di esempio se la directory esiste:
```
La directory esiste.
```

Output di esempio se la directory non esiste:
```
La directory non esiste.
```

Per progetti che non stanno ancora utilizzando C++17 o per caratteristiche aggiuntive, la libreria Boost Filesystem è una scelta di terze parti popolare che offre funzionalità simili.

```cpp
#include <iostream>
#include <boost/filesystem.hpp>

namespace fs = boost::filesystem;

int main() {
    const fs::path dirPath = "/path/to/directory";

    if (fs::exists(dirPath) && fs::is_directory(dirPath)) {
        std::cout << "La directory esiste." << std::endl;
    } else {
        std::cout << "La directory non esiste." << std::endl;
    }

    return 0;
}
```
Usando Boost Filesystem, l'output sarebbe identico all'esempio del filesystem C++17, a seconda dell'esistenza della directory nel percorso specificato.
