---
title:                "CSV के साथ काम करना"
date:                  2024-02-03T19:21:31.545608-07:00
model:                 gpt-4-0125-preview
simple_title:         "CSV के साथ काम करना"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/php/working-with-csv.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?

CSV (Comma-Separated Values) के साथ काम करने का तात्पर्य प्लेन टेक्स्ट में टेबुलर डेटा को प्रस्तुत करने के लिए लोकप्रिय प्रारूप की CSV फाइलों से पढ़ना और उनमें डेटा लिखना शामिल है। प्रोग्रामर इसे विभिन्न प्रोग्रामों, सिस्टमों, या डेटाबेस के बीच डेटा को आसानी से आदान-प्रदान करने के लिए करते हैं, धन्यवाद इसकी सादगी और मंचों और प्रोग्रामिंग भाषाओं में व्यापक समर्थन के लिए।

## कैसे:

PHP में CSV फाइलों को संभालने के लिए निर्मित कार्य उपलब्ध हैं, जिससे इन फाइलों से पढ़ना और इन्हें लिखना तृतीय-पक्ष लाइब्रेरीज़ की आवश्यकता के बिना सरल हो जाता है। आपको शुरुआत करने के लिए यहाँ कुछ उदाहरण दिए गए हैं:

### एक CSV फाइल को पढ़ना

आप `fopen()` का उपयोग करते हुए `fgetcsv()` के संयोजन में एक CSV फाइल खोल सकते हैं और इसकी सामग्री निकाल सकते हैं:

```php
<?php
$filename = 'data.csv';
$handle = fopen($filename, "r");
if ($handle !== FALSE) {
    while (($data = fgetcsv($handle, 1000, ",")) !== FALSE) {
        $num = count($data);
        echo "पंक्ति में क्षेत्रों की संख्या: $num\n";
        for ($c = 0; $c < $num; $c++) {
            echo $data[$c] . "\n";
        }
    }
    fclose($handle);
}
?>
```

यह स्क्रिप्ट प्रत्येक पंक्ति के क्षेत्रों की संख्या के बाद प्रत्येक क्षेत्र की सामग्री प्रिंट करती है।

### एक CSV फाइल में लिखना

CSV फाइल में लिखने के लिए `fopen()` को लिखने के मोड (`w`) में और `fputcsv()` का उपयोग करें:

```php
<?php
$list = [
    ['ID', 'नाम', 'ईमेल'],
    [1, 'जॉन डो', 'john@example.com'],
    [2, 'जेन डो', 'jane@example.com']
];

$handle = fopen('users.csv', 'w');

foreach ($list as $row) {
    fputcsv($handle, $row);
}

fclose($handle);
?>
```

यह स्क्रिप्ट `users.csv` नामक एक फाइल बनाती है और इसमें हैडर और दो डेटा की पंक्तियों को लिखती है।

### लाइब्रेरी का उपयोग: League\Csv

अधिक उन्नत CSV हैंडलिंग के लिए, `League\Csv` लाइब्रेरी एक मजबूत फीचर सेट प्रदान करती है। इसे Composer के माध्यम से इंस्टॉल करने के बाद (`composer require league/csv`), आप इसे अधिक लचीले तरीके से CSV डेटा पढ़ने और लिखने के लिए उपयोग कर सकते हैं।

#### League\Csv के साथ पढ़ना

```php
<?php
require 'vendor/autoload.php';

use League\Csv\Reader;

$csv = Reader::createFromPath('data.csv', 'r');
$csv->setHeaderOffset(0); // पहली पंक्ति को हैडर के तौर पर इस्तेमाल करना चाहते हैं तो सेट करें

$results = $csv->getRecords();
foreach ($results as $row) {
    print_r($row);
}
?>
```

यह स्क्रिप्ट `data.csv` को पढ़ती है, प्रथम पंक्ति को कॉलम हैडरों के रूप में ट्रीट करती है और प्रत्येक पंक्ति को एक एसोसिएटिव एरे के रूप में प्रिंट करती है।

#### League\Csv के साथ लिखना

```php
<?php
require 'vendor/autoload.php';

use League\Csv\Writer;

$csv = Writer::createFromPath('users_new.csv', 'w+');

$csv->insertOne(['ID', 'नाम', 'ईमेल']);
$csv->insertAll([
    [3, 'एलेक्स डो', 'alex@example.com'],
    [4, 'अन्ना स्मिथ', 'anna@example.com']
]);

echo "users_new.csv में सफलतापूर्वक लिखा गया।";
?>
```

यह `users_new.csv` बनाता है और एक हैडर पंक्ति के बाद दो डेटा पंक्तियाँ लिखता है।
