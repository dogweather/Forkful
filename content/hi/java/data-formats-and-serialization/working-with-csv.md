---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:21:16.485946-07:00
description: "CSV \u092B\u093E\u0907\u0932\u094B\u0902 \u0915\u0947 \u0938\u093E\u0925\
  \ \u0915\u093E\u092E \u0915\u0930\u0928\u093E \u0907\u0938\u092E\u0947\u0902 \u0921\
  \u093E\u091F\u093E \u0915\u094B \u092A\u0922\u093C\u0928\u093E \u0914\u0930 \u0915\
  \u0949\u092E\u093E-\u0938\u0947\u092A\u0930\u0947\u091F\u0947\u0921 \u0935\u0948\
  \u0932\u094D\u092F\u0942\u091C\u093C (CSV) \u092B\u093E\u0907\u0932\u094B\u0902\
  \ \u092E\u0947\u0902 \u0921\u093E\u091F\u093E \u0932\u093F\u0916\u0928\u093E \u0936\
  \u093E\u092E\u093F\u0932 \u0939\u0948, \u091C\u094B \u0921\u093E\u091F\u093E \u090F\
  \u0915\u094D\u0938\u091A\u0947\u0902\u091C \u0915\u0947 \u0932\u093F\u090F \u090F\
  \u0915 \u0932\u094B\u0915\u092A\u094D\u0930\u093F\u092F \u092A\u094D\u0930\u093E\
  \u0930\u0942\u092A\u2026"
lastmod: '2024-03-13T22:44:52.152449-06:00'
model: gpt-4-0125-preview
summary: "CSV \u092B\u093E\u0907\u0932\u094B\u0902 \u0915\u0947 \u0938\u093E\u0925\
  \ \u0915\u093E\u092E \u0915\u0930\u0928\u093E \u0907\u0938\u092E\u0947\u0902 \u0921\
  \u093E\u091F\u093E \u0915\u094B \u092A\u0922\u093C\u0928\u093E \u0914\u0930 \u0915\
  \u0949\u092E\u093E-\u0938\u0947\u092A\u0930\u0947\u091F\u0947\u0921 \u0935\u0948\
  \u0932\u094D\u092F\u0942\u091C\u093C (CSV) \u092B\u093E\u0907\u0932\u094B\u0902\
  \ \u092E\u0947\u0902 \u0921\u093E\u091F\u093E \u0932\u093F\u0916\u0928\u093E \u0936\
  \u093E\u092E\u093F\u0932 \u0939\u0948, \u091C\u094B \u0921\u093E\u091F\u093E \u090F\
  \u0915\u094D\u0938\u091A\u0947\u0902\u091C \u0915\u0947 \u0932\u093F\u090F \u090F\
  \u0915 \u0932\u094B\u0915\u092A\u094D\u0930\u093F\u092F \u092A\u094D\u0930\u093E\
  \u0930\u0942\u092A \u0939\u0948 \u0915\u094D\u092F\u094B\u0902\u0915\u093F \u092F\
  \u0939 \u0938\u0930\u0932 \u0939\u0948 \u0914\u0930 \u0935\u094D\u092F\u093E\u092A\
  \u0915 \u0930\u0942\u092A \u0938\u0947 \u0938\u092E\u0930\u094D\u0925\u093F\u0924\
  \ \u0939\u0948\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\
  \u094D\u0938 CSV \u092B\u093E\u0907\u0932\u094B\u0902 \u0915\u093E \u092E\u0948\u0928\
  \u093F\u092A\u0941\u0932\u0947\u0936\u0928 \u0921\u093E\u091F\u093E \u0907\u092E\
  \u094D\u092A\u094B\u0930\u094D\u091F/\u090F\u0915\u094D\u0938\u092A\u094B\u0930\u094D\
  \u091F, \u0921\u093E\u091F\u093E \u0935\u093F\u0936\u094D\u0932\u0947\u0937\u0923\
  , \u0914\u0930 \u0935\u093F\u092D\u093F\u0928\u094D\u0928 \u0938\u093F\u0938\u094D\
  \u091F\u092E\u094B\u0902 \u0915\u0947 \u092C\u0940\u091A \u091C\u093E\u0928\u0915\
  \u093E\u0930\u0940 \u0938\u093E\u091D\u093E \u0915\u0930\u0928\u0947 \u091C\u0948\
  \u0938\u0947 \u0915\u093E\u0930\u094D\u092F\u094B\u0902 \u0915\u0947 \u0932\u093F\
  \u090F \u0915\u0930\u0924\u0947 \u0939\u0948\u0902\u0964."
title: "CSV \u0915\u0947 \u0938\u093E\u0925 \u0915\u093E\u092E \u0915\u0930\u0928\u093E"
weight: 37
---

## कैसे करें:


### मानक जावा पुस्तकालय का उपयोग करके CSV फाइल पढ़ना
जावा के मानक पुस्तकालय में CSV के लिए बिल्ट-इन सपोर्ट नहीं है, लेकिन आप `java.io` वर्गों का उपयोग करके आसानी से CSV फाइल पढ़ सकते हैं।

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class ReadCSVExample {
    public static void main(String[] args) {
        String line;
        String csvFile = "data.csv"; // CSV फाइल के पथ को निर्दिष्ट करें
        try (BufferedReader br = new BufferedReader(new FileReader(csvFile))) {
            while ((line = br.readLine()) != null) {
                String[] values = line.split(","); // मानते हुए कि एक कॉमा ही विभाजक है
                // डाटा प्रोसेस करें
                for (String value : values) {
                    System.out.print(value + " ");
                }
                System.out.println();
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### मानक जावा पुस्तकालय का उपयोग करके CSV फाइल में लिखना
CSV फाइल में डेटा लिखने के लिए, आप `java.io` वर्गों जैसे `FileWriter` और `BufferedWriter` का उपयोग कर सकते हैं।

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class WriteCSVExample {
    public static void main(String[] args) {
        String[] data = {"John", "Doe", "30", "New York"};
        String csvFile = "output.csv"; // आउटपुट CSV फाइल पथ को निर्दिष्ट करें

        try (BufferedWriter bw = new BufferedWriter(new FileWriter(csvFile))) {
            StringBuilder sb = new StringBuilder();
            for (String value : data) {
                sb.append(value).append(","); // मानते हुए कि एक कॉमा ही विभाजक है
            }
            sb.deleteCharAt(sb.length() - 1); // आखिरी कॉमा हटाएं
            bw.write(sb.toString());
            bw.newLine();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### थर्ड पार्टी पुस्तकालय का उपयोग: अपाचे कॉमन्स CSV
अपाचे कॉमन्स CSV जावा में CSV फाइलों को हैंडल करने के लिए एक लोकप्रिय पुस्तकालय है। यह CSV फाइलों को पढ़ने और लिखने को काफी सरल बना देता है।

अपने प्रोजेक्ट में निर्भरता जोड़ें:

मेवेन के लिए:

```xml
<dependency>
    <groupId>org.apache.commons</groupId>
    <artifactId>commons-csv</artifactId>
    <version>1.9.0</version> <!-- नवीनतम संस्करण के लिए जांचें -->
</dependency>
```

#### एक CSV फाइल पढ़ना:
```java
import org.apache.commons.csv.CSVFormat;
import org.apache.commons.csv.CSVParser;
import org.apache.commons.csv.CSVRecord;

import java.io.Reader;
import java.io.FileReader;
import java.io.IOException;

public class ApacheReadCSVExample {
    public static void main(String[] args) {
        String csvFile = "data.csv";
        try (Reader reader = new FileReader(csvFile);
             CSVParser csvParser = new CSVParser(reader, CSVFormat.DEFAULT)) {
            for (CSVRecord csvRecord : csvParser) {
                // कॉलम के इंडेक्सेज़ से मानों को एक्सेस करना
                String columnOne = csvRecord.get(0);
                String columnTwo = csvRecord.get(1);
                System.out.println(columnOne + " " + columnTwo);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

#### एक CSV फाइल में लिखना:
```java
import org.apache.commons.csv.CSVFormat;
import org.apache.commons.csv.CSVPrinter;

import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class ApacheWriteCSVExample {
    public static void main(String[] args) {
        String[] headers = {"First Name", "Last Name", "Age", "City"};
        String[] data = {"John", "Doe", "30", "New York"};

        try (BufferedWriter writer = new BufferedWriter(new FileWriter("output.csv"));
             CSVPrinter csvPrinter = new CSVPrinter(writer, CSVFormat.DEFAULT.withHeader(headers))) {
            csvPrinter.printRecord((Object[]) data); // यहाँ Object[] को कास्ट करना आवश्यक है
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

अपाचे कॉमन्स CSV खेतों के भीतर उद्धरण और कॉमा जैसी जटिलताओं को स्वचालित रूप से संभालता है, जो इसे जावा में CSV मैनिपुलेशन के लिए एक मजबूत विकल्प बनाता है।
