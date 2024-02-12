---
title:                "Väliaikaistiedoston luominen"
aliases:
- fi/java/creating-a-temporary-file.md
date:                  2024-01-20T17:40:41.887926-07:00
model:                 gpt-4-1106-preview
simple_title:         "Väliaikaistiedoston luominen"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/java/creating-a-temporary-file.md"
---

{{< edit_this_page >}}

## What & Why? (Mitä & Miksi?)
Luodaan väliaikainen tiedosto – se on tiedosto, joka poistuu automaattisesti, kun sitä ei enää tarvita. Ohjelmoijat tekevät näin tilapäisen tallennustilan tarpeessa ja turvallisuussyistä, kuten salasanojen käsittelyssä.

## How to: (Kuinka tehdään:)
```java
import java.io.File;
import java.io.IOException;
import java.nio.file.Files;

public class TemporaryFileExample {
    public static void main(String[] args) {
        try {
            // Luo väliaikainen tiedosto
            File tempFile = Files.createTempFile("myapp-", ".tmp").toFile();
            
            // Näytä tiedoston polku
            System.out.println("Temporary file created at: " + tempFile.getAbsolutePath());
            
            // Do something with the file...
            
            // Delete the file when the program ends
            // Poista tiedosto ohjelman lopussa
            tempFile.deleteOnExit();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```
Sample output:
```
Temporary file created at: /var/folders/yb/yp_xxxxmyapp-xxxxxx.tmp
```

## Deep Dive (Sukellus syvyyksiin):
Väliaikaisen tiedoston luominen on ollut osa Javaa version 1.2 alkaen, mutta vuosien varrella API on kehittynyt ja tarjoaa nyt `Files.createTempFile` -metodin, joka on nykyaikainen ja helppokäyttöinen. Vaihtoehtoja on monia: voit määritellä polun, tiedoston nimen, jatkeen ja jopa käyttää `File.createTempFile` vanhempaa metodia. Väliaikaisten tiedostojen hallinta Java-ohjelmissa on yksinkertaista, mutta varmista, että tiedot ovat suojattuja ja tiedostot poistetaan, kun niitä ei enää tarvita.

## See Also (Katso myös):
- [Java Docs: Files.createTempFile](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/nio/file/Files.html#createTempFile(java.nio.file.Path,java.lang.String,java.lang.String,java.nio.file.attribute.FileAttribute...))
