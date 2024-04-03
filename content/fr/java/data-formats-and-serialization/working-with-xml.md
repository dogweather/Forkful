---
date: 2024-01-26 04:32:19.814733-07:00
description: "Travailler avec XML implique d'analyser, d'interroger et de manipuler\
  \ des documents XML avec Java. Les programmeurs le font pour l'\xE9change de donn\xE9\
  es, la\u2026"
lastmod: '2024-03-13T22:44:57.669869-06:00'
model: gpt-4-0125-preview
summary: Travailler avec XML implique d'analyser, d'interroger et de manipuler des
  documents XML avec Java.
title: Travailler avec XML
weight: 40
---

## Comment faire :
Java fournit des API comme DOM (Document Object Model), SAX (Simple API for XML), et StAX (Streaming API for XML) pour travailler avec XML. Voici un exemple DOM pour analyser un fichier XML :

```java
import javax.xml.parsers.DocumentBuilder;
import javax.xml.parsers.DocumentBuilderFactory;
import org.w3c.dom.Document;
import org.w3c.dom.Element;
import org.w3c.dom.NodeList;

public class XmlParser {
    public static void main(String[] args) {
        try {
            DocumentBuilderFactory factory = DocumentBuilderFactory.newInstance();
            DocumentBuilder builder = factory.newDocumentBuilder();
            Document doc = builder.parse("data.xml");
            
            doc.getDocumentElement().normalize();
            NodeList nodeList = doc.getElementsByTagName("employee");
            
            for (int i = 0; i < nodeList.getLength(); i++) {
                Element element = (Element) nodeList.item(i);
                System.out.println("Nom : " + element.getElementsByTagName("name").item(0).getTextContent());
                System.out.println("Âge : " + element.getElementsByTagName("age").item(0).getTextContent());
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

Supposons que `data.xml` ressemble à cela :

```xml
<employees>
    <employee>
        <name>Jane Doe</name>
        <age>30</age>
    </employee>
    <employee>
        <name>John Doe</name>
        <age>40</age>
    </employee>
</employees>
```

Le résultat serait :

```
Nom : Jane Doe
Âge : 30
Nom : John Doe
Âge : 40
```

## Plongée Profonde
XML existe depuis la fin des années 90, offrant une manière structurée et flexible d'échanger des données à travers différents systèmes. Bien que JSON soit devenu plus populaire pour les nouvelles API web en raison de sa syntaxe plus simple et de son intégration étroite avec JavaScript, XML reste largement utilisé dans les environnements d'entreprise, les services web basés sur SOAP, et les normes documentaires comme Office Open XML pour Microsoft Office.

Quand il s'agit d'analyser XML en Java, l'API DOM est excellente pour les documents plus petits : elle est basée sur un arbre et permet un accès complet à la structure XML en mémoire. Cependant, pour les fichiers plus importants, cela peut être gourmand en mémoire. SAX et StAX sont plus économes en mémoire, car ils sont événementiels et basés sur le flux respectivement, mais ils peuvent être moins pratiques pour naviguer dans les structures XML.

Pour créer ou modifier XML, Java fournit également les packages javax.xml.transform et javax.xml.bind (JAXB). JAXB faisait partie de Java SE jusqu'à la version 10, après quoi, il est devenu une bibliothèque à part en raison du retrait des modules Java EE de Java SE. C'est une manière dirigée par annotation de sérialiser des objets Java en XML et vice versa.

## Voir Aussi
Consultez ces sources connexes pour en savoir plus sur le travail avec XML en Java :
- [Java API for XML Processing (JAXP)](https://docs.oracle.com/javase/8/docs/technotes/guides/xml/jaxp/index.html)
- [Java Architecture for XML Binding (JAXB)](https://javaee.github.io/jaxb-v2/)
- [Guide Oracle pour XML en Java](https://docs.oracle.com/javase/tutorial/jaxp/index.html)
- [Technologie XML du W3C](https://www.w3.org/standards/xml/)
- [Stack Overflow : Questions taguées 'java' et 'xml'](https://stackoverflow.com/questions/tagged/java+xml)
